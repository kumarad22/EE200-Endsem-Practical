
# 📁 EE200 Endsem Practical Project

### 🧩 Overview

This project is divided into **two main tasks** that explore signal processing using the Discrete Fourier Transform (DFT), frequency-domain filtering, and digital filtering techniques.

- **Q1: Frequency Mixer – "Beauty and the Blur"**  
  Combine two images into a single hybrid image by manipulating their frequency components.
  
- **Q2: Frequency De-mixer – "Unwanted Solo"**  
  Denoise an audio signal using Butterworth filters and time-frequency analysis.

---

### 📷 Question 1 – Hybrid Image Generation

#### 🔬 Objective
Create a **hybrid image** by fusing:
- a **low-pass filtered image** (retains smooth features)
- a **high-pass filtered image** (retains edges and details)

#### ⚙️ Steps
1. Convert the given RGB grayscale images to single-channel format.
2. Compute the **2D FFT** of both images and center the low frequencies.
3. Apply:
   - **Gaussian low-pass filter** to one image
   - **Gaussian high-pass filter** to the other
4. Take the inverse FFT to recover spatial-domain filtered images.
5. **Fuse** the images with tuned weights to get a hybrid image:
   - `w_low = 0.6`
   - `w_high = 0.4`
6. Visualize the magnitude spectra and downsampled outputs.

---

### 🎵 Question 2 – Audio Denoising

#### 🔬 Objective
Remove **unwanted instrumental components** from an audio signal by analyzing and filtering in the frequency domain.

#### ⚙️ Steps
1. Load and normalize the audio.
2. Plot:
   - **Waveform**
   - **Spectrogram (STFT)**
   - **FFT magnitude spectrum**
   - **Power Spectral Density (PSD)** using Welch's method
3. Identify **noisy frequency bands** (~1000 Hz to 6000 Hz).
4. Apply a **Butterworth bandstop filter** with:
   - order = 6  
   - cutoff = [1000 Hz, 6000 Hz]
5. Re-plot FFT, STFT, and PSD for the filtered signal.

---

### 🧪 Results

#### ✅ Image Task
- Successfully produced a hybrid image perceptible differently from near and far distances.
- Used frequency-domain visualizations to confirm component contributions.

#### ✅ Audio Task
- High-energy frequencies identified and removed via filtering.
- Resulting signal showed **significant noise suppression** in the stopband.

---

### 📎 Resources & References

1. **Oliva, A., Torralba, A., & Schyns, P. G.** (2006). *Hybrid Images*. ACM Transactions on Graphics, 25(3), 527–532.
2. **Cooley, J. W., & Tukey, J. W.** (1965). *An Algorithm for the Machine Calculation of Complex Fourier Series*. Mathematics of Computation, 19(90), 297–301.
3. **Butterworth, S.** (1930). *On the Theory of Filter Amplifiers*. Wireless Engineer, 7(6), 536–541.

---

### ▶️ Install Dependencies
 
```bash
pip install numpy scipy matplotlib librosa soundfile opencv-python
