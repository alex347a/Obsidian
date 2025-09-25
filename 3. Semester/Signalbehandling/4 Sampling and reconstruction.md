If you look at exercise 2 for lection 3 you can see for the bandpass filter the waves are kind of oscillating or at least increasing with time, this is because when N is 5 it has to pass a bigger system and therefore the signal starts at 0 and increases with time.

### Continuous - discrete (C/D) converter
This concept is VERY IMPORTANT
![[Pasted image 20250925084647.png]]

### Time domain
![[Pasted image 20250925084655.png]]
$p(t)$ is an impulse sequence. T is the sampling period. n is the amount of samples. $*$ is not a star its just a $\cdot$ its NOT A CONVOLUTION. So you just take different points of the graph, you don't care how the graph actually looks between the dots.

![[Pasted image 20250925085050.png]]
If the signal is periodic it can be represented as a Fourier transform where $C_{m}$ is the Fourier coefficient. Since the impulse signal is also periodic, it can also be Fourier transformed.
![[Pasted image 20250925085617.png]]
Remember here $*$ is wrong, it's just $\cdot$
The equation means you only have one symmetric shape until you do your pulse sampling, which then repeats the shape:
![[Pasted image 20250925090015.png]]
m is the index for the frequency copies, so $m=0$ is the original.
![[Pasted image 20250925091811.png]]
A discrete signal in the time domain becomes a periodic spectra in the frequency domain. For example a square wave becomes a sinusoidal.
A periodic signal in the time domain becomes a discrete spectra in the frequency domain. For example a sinusoidal becomes a square.
![[Pasted image 20250925092423.png]]
Aliasing is when the sample frequency is too low so the repeated spectra overlaps.
![[Pasted image 20250925092838.png]]
![[Pasted image 20250925092845.png]]
Your sampling frequency must always be at least twice the highest frequency in the spectrum for $x(t)$
### Nyquist frequency: $\frac{f_{s}}{2}$ 
![[Pasted image 20250925093245.png]]
The typical value is about 20%.

![[Pasted image 20250925093712.png]]
Only pulse amplitude modulation is discussed in this course.
![[Pasted image 20250925093829.png]]
![[Pasted image 20250925093834.png]]
![[Pasted image 20250925094046.png]]
![[Pasted image 20250925094345.png]]
As you can see the amplitude changes with pulse-sampling.
![[Pasted image 20250925095338.png]]
As you can see in the second impulse sampling spectrum is the aliasing problem, because the sampling rate is only 200 Hz while the highest frequency is 120 Hz.
![[Pasted image 20250925101133.png]]
![[Pasted image 20250925101449.png]]
![[Pasted image 20250925101620.png]]
Reconstruction is when you want to go from a discrete/digital signal to an analogue/continuos signal, so you have a value for the amplitude at every time, and not just at your sampling times.
![[Pasted image 20250925102034.png]]
So you just set the value between two points to the value of the point before the next point.
![[Pasted image 20250925102141.png]]
![[Pasted image 20250925102306.png]]
The striped line is the original signal. The lowpass filter is at 4 because it is half of the sampling frequency at 8 kHz. 

### MANGLER ET SLIDE DER HEDDER CORRECTION OF AMPLITUDE RESPONSE.

You add the reciprocal of the function to your reconstruction filter to compensate of the attenuation because of the zero hold. This makes a better filter than using a low pass filter, since the low pass filter filters all of the high frequencies out completely.

Chatten:
### Step 1: The Problem - The Zero-Order Hold (ZOH)

When a digital signal is converted to an analog one, the most common method is the **Zero-Order Hold (ZOH)**.

- **What it does:** The DAC takes each digital sample value and holds it constant until the next sample is available. This creates a "stair-step" waveform.
    
- **The Issue (Spectral Attenuation):** This holding process isn't perfect. It acts like a filter itself, and it has a specific frequency response. This response **attenuates** (weakens) frequencies in the desired signal _even before they leave the DAC_.
    

The frequency response (how much it attenuates at a given frequency, *f*) of the ZOH is given by the **sinc function**:  
`H_zoh(f) = T * sinc(f * T) = T * (sin(πfT) / (πfT))`  
where `T` is the sampling period.

- **Key Point:** At the fundamental frequency (f=0), there is no attenuation. But as the frequency increases, the attenuation gets worse. This happens **within the Nyquist bandwidth (0 to f_s/2)**! So, your desired high-frequency components are already quieter than they should be.
    

### Step 2: The Naive Solution - The Standard Low-Pass Filter (and why it's not great)

The next step in a DAC is always a **Reconstruction Filter** (a low-pass filter). Its main job is to remove the high-frequency "images" of the digital signal that are centered around multiples of the sampling rate.

- **What it does:** A standard, or "brick-wall," low-pass filter is designed to pass all frequencies from 0 to f_s/2 perfectly and block all frequencies above f_s/2 completely.
    
- **The Problem with this approach:** As you correctly noted, this filter does **nothing** to fix the attenuation caused by the ZOH. It simply passes the already-attenuated signal. The result is a final analog signal where the high-frequency content is permanently lost or diminished. The signal will sound or look "dull" or "muffled."
    

### Step 3: The Smart Solution - The Compensating Reconstruction Filter

This is where your explanation comes in. To get a perfect reconstruction, we need a filter that does two jobs:

1. **Compensate** for the ZOH's attenuation.
    
2. **Remove** the high-frequency images.
    

We can build a single filter that does both. This is the "better filter" you're describing.

**The "Reciprocal" You Mentioned**

The ideal compensation would be to apply a filter that has the exact opposite effect of the ZOH. This is the **reciprocal** of the ZOH's frequency response.

- **Compensation Filter Response:** `H_comp(f) = 1 / H_zoh(f) = 1 / (T * sinc(fT))`
    

If you cascade (put one after the other) the ZOH and this compensation filter, their combined effect would be `H_zoh(f) * H_comp(f) = 1`. This means the signal passes through perfectly with no distortion!

**Combining Compensation with Anti-Imaging**

In practice, we combine this compensation with the necessary low-pass filtering. The ideal, combined **Reconstruction Filter** would have a response that is the product of the compensation response and the ideal low-pass response:

`H_ideal_recon(f) = H_comp(f) * H_lowpass(f) = (1 / (T * sinc(fT))) * [1 for |f| < f_s/2, 0 for |f| > f_s/2]`

**What this means in practice:** Instead of being flat up to f_s/2, this filter has a **gentle, rising gain** as the frequency approaches f_s/2. This rising gain precisely counteracts the falling gain (sinc) of the ZOH.
### Summary: Analogy
Think of it like an audio system:
- **The ZOH** is like a bad speaker that can't reproduce high frequencies well (it has a weak "treble" response).
- **The Standard Low-Pass Filter** is like turning up the volume. The weak treble from the speaker just gets louder, but it's still weak compared to the bass.
- **The Compensating Filter** is like using a **graphic equalizer** on your stereo. You turn up _just the treble_ to compensate for the bad speaker _before_ the sound even gets to it. The final result is a balanced, full-frequency sound.
### Why is this "Better"?

Your final point is exactly right. Using a compensating filter is better because:

1. **It Preserves Fidelity:** It correctly reconstructs the _entire_ frequency content of the original signal (within 0 to f_s/2), not just the low-frequency parts. The high frequencies are restored to their proper amplitude.
2. **It's More Accurate:** The goal of reconstruction is to get as close as possible to the original analog signal before it was sampled. A compensating filter gets you much closer than a simple low-pass filter.

In real-world DAC chips, this compensation is often a built-in characteristic of the analog output filter.

|Feature|Standard Low-Pass Filter|Compensating Reconstruction Filter|
|---|---|---|
|**Main Goal**|Remove high-frequency images.|Remove images **and** correct for ZOH distortion.|
|**Frequency Response**|Flat up to f_s/2.|Gently rising gain as frequency approaches f_s/2.|
|**Resulting Signal**|Muffled, high frequencies are attenuated.|More accurate, full-frequency representation of the original signal.|
|**Analogy**|Turning up the volume on a bad speaker.|Using an equalizer to fix the speaker's response.|
### 
Multiplying in the time domain is the convolution in the frequency domain and vice versa.

