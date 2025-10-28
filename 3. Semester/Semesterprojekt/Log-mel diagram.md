1. The audio is sampled at a fixed sampling rate to amplitude values.
2. The values are converted into spectrogram by using a Short-Time Fourier Transform, which is the wave is broken into tiny windows and Fourier transformed, so we know how much of each specific frequency there is present. Then a spectrogram is created where the x-axis is time, the y-axis is frequency and the z-axis is the magnitude of each frequency (given by different colors)
3. The spectrogram are converted into Mel-spectrogram, which uses a logarithmic scale to emulate human hearing, because humans have a non-linear response. The linear frequencies are grouped into filters that are spread across the mel-warped frequency axis, which compresses the data so we have high resolution at lower frequency ranges and low resolution at higher frequency ranges. (An example of how this is done could be included, check #2)


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

$$\text{Energy in Mel Band k} = \sum (\text{Magnitude}[\text{linear_bin_i}] \cdot \text{Weight_of_Filter_k}[\text{linear_bin_i}])$$

We repeat this for all 80 filters. The result for time frame `t` is a vector of 80 values, not 256.

### The "Compression" and "Alignment" Explained

1. **"Averages the energy in critical frequency bands":** Instead of knowing the exact energy at 100Hz, 101Hz, 102Hz, etc., we now know the _total energy_ in the "band of small fish" (e.g., 0-200Hz). We've gone from 256 precise measurements to 80 broader, more perceptually relevant summaries.
    
2. **"Effectively compressing the data":** We've reduced the dimensionality from 256 frequency bins to 80 Mel bins. This is a form of lossy compression that throws away information that is less useful for speech recognition (like fine-grained frequency details at high frequencies).
    
3. **"Making it more aligned with human auditory perception":** This is the key. By using the Mel scale, we ensure that:
    
    - **At low frequencies,** we have high resolution (many filters in a small Hz range), which matches our ear's ability to distinguish fine differences in pitch.
        
    - **At high frequencies,** we have low resolution (fewer filters spread over a large Hz range), which matches our ear's decreasing sensitivity to fine pitch differences.