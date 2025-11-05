1. The audio is sampled at a fixed sampling rate to amplitude values.
2. The values are converted into spectrogram by using a Short-Time Fourier Transform, which is the wave is broken into tiny windows and Fourier transformed, so we know how much of each specific frequency there is present. Then a spectrogram is created where the x-axis is time, the y-axis is frequency and the z-axis is the magnitude of each frequency (given by different colours)
3. The spectrogram are converted into Mel-spectrogram, which is a scale that approximates the non-linear response humans have to sound. The linear frequencies are grouped into filters that are spread across the mel-warped frequency axis, which compresses the data so we have high resolution at lower frequency ranges and low resolution at higher frequency ranges. (An example of how this is done could be included, check #2)
4. The Mel-spectrogram is converted into a logarithmic scale of the magnitudes, because humans hear a sound twice as loud only if the sound is 10 times more powerful.


### How whisper processes the Log-mel spectrogram
#### 1. The Encoder

- The log-mel spectrogram is passed through a small stack of convolutional layers. Think of these as layers that can detect simple patterns (like edges) in the first layer, and progressively more complex patterns (like formants, which are crucial for vowel sounds) in deeper layers.
    
- The output of these convolutions is then fed into the main part of the Encoder, which is a Transformer network. The Transformer's self-attention mechanism allows it to see the _context_ for every time step. For example, to understand a mumbled syllable, it can "pay attention" to the clear syllables that come before and after it.
    
- The encoder's job is to transform the input spectrogram into a high-level, contextualized representation—a sequence of feature vectors that encapsulate "what was said."
    

#### 2. The Decoder

- The decoder is also a Transformer network. It is responsible for generating the text, one token (word/subword) at a time.
    
- It starts with a special **start-of-transcript** token.
    
- To generate the next token, it uses two sources of information:
    
    1. **The Encoder's Output:** It "cross-attends" to the encoded audio features to understand what it should be saying.
        
    2. **The Previously Generated Tokens:** It uses self-attention on the text it has already produced to ensure grammatical coherence and consistency.
        
- This process is auto-regressive—the newly generated token is appended to the sequence and fed back in to generate the next one, until an **end-of-transcript** token is produced.
    

### Part 3: What Makes Whisper Special? Multitask Training

Whisper's remarkable robustness doesn't just come from its architecture, but from its training. It was trained on a massive dataset of 680,000 hours of audio from the web, covering a vast range of accents, languages, recording conditions, and topics.

Crucially, it was trained as a **multitask model**. The training data included various "tasks" like:

- Transcription in the original language.
    
- Translation to English.
    
- Voice activity detection (identifying when speech starts and stops).
    
- Language identification.
    

During training, Whisper is given special tokens that tell the decoder _what task to perform_. For example:

- `<|startoftranscript|><|en|><|transcribe|>` means "Start, the language is English, transcribe it."
    
- `<|startoftranscript|><|fr|><|translate|>` means "Start, the source language is French, translate it to English."
    

This is why a single Whisper model is so versatile. The decoder learns to condition its output on these instructions, allowing it to perform transcription, translation, and language ID seamlessly.

### Summary: The Complete Whisper Pipeline

1. **Pre-processing:** Audio file is loaded and converted to a 16kHz mono waveform.
    
2. **Feature Extraction:** The waveform is converted into an **80-channel log-mel spectrogram**.
    
3. **Encoding:** The spectrogram is passed through the Encoder (Convolutions + Transformer), which converts it into a rich, contextualized representation.
    
4. **Decoding:** The Decoder, guided by a task-specific prompt (e.g., "transcribe to English"), auto-regressively generates the text output by attending to both the encoder's output and its own previous tokens.
    
5. **Output:** The sequence of tokens is converted back into human-readable text.
    

The **log-mel spectrogram** is the critical bridge that transforms the chaotic world of sound waves into a structured, perceptually-relevant "image" that the Transformer model can successfully learn from and process.

# 2
#### Step 1: We have a Linear Spectrogram

Imagine your spectrogram has 256 frequency bins, spread equally from 0Hz to 8000Hz. It's very detailed.

#### Step 2: Create the Mel Filter Bank (The "Nets")

We create a set of triangular filters (typically 80 of them, as mentioned for Whisper) on the Mel scale. Here's how:

1. **Convert the Frequency Range to Mel Scale:** First, we convert our min and max frequencies (e.g., 0Hz and 8000Hz) to their Mel equivalents. This warps the frequency axis, "stretching" the low frequencies and "compressing" the high frequencies.
    
2. **Space the Filters Evenly on the Mel Scale:** We create, say, 80 points equally spaced along this new warped Mel axis.
    
3. **Convert Back to Linear Frequency:** We convert these 80 Mel points back to the linear frequency scale (Hz). This gives us the _center frequencies_ for our 80 filters on the original linear scale. You'll notice that in Hz, these points are very close together at low frequencies and much farther apart at high frequencies.
    
4. **Build the Triangular Filters:** For each of these 80 center points, we create a triangular filter.
    
    - The peak of the triangle is at the center frequency (`f_center`).
        
    - The base of the triangle starts at the center frequency of the previous filter (`f_left`) and ends at the center frequency of the next filter (`f_right`).
        
    - The height of the triangle is normalized to 1.
        

This results in a set of 80 overlapping triangular windows. Visually, it looks like this (though with 80 triangles, it would be much denser on the left):

![[Pasted image 20251028111830.png]]

#### Step 3: Apply the Filters (The "Catching")

Now, we take our detailed linear spectrogram (with its 256 bins) and pass it through each of these 80 Mel filters.

For a single time frame `t`:

- We have a vector of 256 magnitude values (the "power" in each of the 256 linear frequency bins).
    
- For **Mel filter #k**, we calculate its output. This is a weighted average:
    
    - We multiply each of the 256 magnitude values by the corresponding height (the weight) of the triangular filter #k at that frequency.
        
    - We sum up all these weighted values.
        

**What does this sum represent?** It represents the **total amount of energy** present in the frequency band covered by that specific Mel filter.

$$\text{Energy in Mel Band k} = \sum (\text{Magnitude}(\text{linear} \textunderscore \text{bin} \textunderscore \text{i}) \cdot \text{Weight} \textunderscore \text{of} \textunderscore \text{filter} \textunderscore \text{k}(\text{linear} \textunderscore \text{bin} \textunderscore \text{i}))$$
We repeat this for all 80 filters. The result for time frame `t` is a vector of 80 values, not 256.
### The "Compression" and "Alignment" Explained

1. **"Averages the energy in critical frequency bands":** Instead of knowing the exact energy at 100Hz, 101Hz, 102Hz, etc., we now know the _total energy_ in the "band of small fish" (e.g., 0-200Hz). We've gone from 256 precise measurements to 80 broader, more perceptually relevant summaries.
    
2. **"Effectively compressing the data":** We've reduced the dimensionality from 256 frequency bins to 80 Mel bins. This is a form of lossy compression that throws away information that is less useful for speech recognition (like fine-grained frequency details at high frequencies).
    
3. **"Making it more aligned with human auditory perception":** This is the key. By using the Mel scale, we ensure that:
    
    - **At low frequencies,** we have high resolution (many filters in a small Hz range), which matches our ear's ability to distinguish fine differences in pitch.
        
    - **At high frequencies,** we have low resolution (fewer filters spread over a large Hz range), which matches our ear's decreasing sensitivity to fine pitch differences.