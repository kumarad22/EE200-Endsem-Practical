# 🎧📷 EE200 Endsem Practical – Hybrid Images & Audio Denoising

> A dual-part project demonstrating frequency-domain processing using Discrete Fourier Transform (DFT) on both images and audio signals.

---

## 📌 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Part 1: Image Hybridization](#part-1-image-hybridization)
- [Part 2: Audio Denoising](#part-2-audio-denoising)
- [Usage](#usage)
- [Results](#results)
- [References](#references)
- [Author](#author)

---

## 🧠 Overview

This project explores frequency-domain filtering techniques using both 2D and 1D Discrete Fourier Transform (DFT) and Short-Time Fourier Transform (STFT) for two distinct applications:

- 📷 **Image Hybridization** — combining the low-frequency content of one image and the high-frequency content of another.
- 🎧 **Audio Denoising** — cleaning noisy audio using spectral gating, bandpass filters, and FFT-based techniques.

---

## ✨ Features

- FFT-based hybrid image creation
- Gaussian low-pass and high-pass filters
- Centered FFT visualization
- Multiple audio denoising pipelines using:
  - Spectral Gating
  - FFT Thresholding
  - Bandpass + Thresholding
  - Combined Techniques
- Bode magnitude plots and visual FFT interpretation
- STFT-based dynamic frequency analysis

---

## 🛠️ Technologies Used

- Python
- NumPy
- SciPy
- Matplotlib
- Librosa
- Jupyter Notebook (for development & visualization)

---

## 📷 Part 1: Image Hybridization – *Beauty and the Blur*

### 🔍 Method Summary

- Convert grayscale images to single channel
- Apply FFT, center-shift, and visualize magnitude
- Apply Gaussian filters:
  - High-pass (σ=5) to the cat image
  - Low-pass (σ=20) to the dog image
- Perform inverse FFT to get filtered images
- Fuse filtered images with weights:  
  `final_image = 0.4 × high_freq + 0.6 × low_freq`

### 📸 Visual Outputs

- Original FFT spectra
- Rotated & filtered FFTs
- Hybrid image output (raw + downsampled)

---

## 🎧 Part 2: Audio Denoising – *Unwanted Solo*

### 🎼 Pre-processing

- Read noisy audio file using Librosa
- Normalize and plot waveform and spectrogram
- Compute DFT and STFT

### 🎚️ Denoising Techniques

1. **Spectral Gating Only**
2. **FFT Magnitude Thresholding**
3. **Bandpass Filtering + Magnitude Threshold**
4. **Combined Approach (All Above)**

### 🔊 Output Files

- `output_a_spectral_gating.wav`
- `output_b_fft_threshold.wav`
- `output_c_bandpass_fft_thresh.wav`
- `output_d_combined.wav`

Each output demonstrates varying levels of improvement in clarity.

---

## 🚀 Usage

### 1. Install Dependencies

```bash
pip install numpy scipy matplotlib librosa
