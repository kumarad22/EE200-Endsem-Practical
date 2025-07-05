# 🎧📷 EE200 Endsem Practical – Hybrid Images & Audio Denoising

> A dual-part project demonstrating frequency-domain processing using Discrete Fourier Transform (DFT) on both images and audio signals.

---

## 📌 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Part 1: Image Hybridization](#part-1-image-hybridization)
- [Part 2: Audio Denoising](#part-2-audio-denoising)

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
- Compute FFT, STFT and PSD and plot them

### 🎚️ Denoising Techniques

1. **Identified frequencies range where most of the noise content was present through PSD & FFT plots**
2. **Designed a Butterworth Bandstop Filter to suppress these frequencies, got a much clearer output**
3. **Computed FFT, STFT and PSD and drew their plots once again after applying filter**

---

### 1. Install Dependencies

```bash
pip install numpy scipy matplotlib librosa
