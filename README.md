# 🏋️ Surface EMG Muscle Fatigue Analysis

An end-to-end signal processing mini-project in Python that detects and quantifies muscle fatigue from Surface Electromyography (sEMG) signals using frequency-domain analysis.

---

## 📌 Project Overview
During sustained muscle contraction, metabolic accumulation reduces muscle fiber conduction velocity. In a surface electromyography (sEMG) recording, this manifests as **spectral compression**—a gradual shift of the electrical signal toward lower frequencies over time.

This project implements a complete biomedical signal processing pipeline to:
1. Filter motion artifacts and electrical powerline noise.
2. Segment sEMG signals using sliding time windows.
3. Compute **Median Frequency (MDF)** and **Mean Frequency (MNF)** using Welch's Power Spectral Density (PSD) estimation.
4. Fit a linear regression model to calculate the **Fatigue Slope (Hz/s)**.

---

## ⚙️ Processing Pipeline
[ Raw sEMG Signal ]
↓
[ Bandpass Filter (20-450 Hz) & Notch Filter (60 Hz) ]
↓
[ Epoching: 1.0s Window with 50% Overlap ]
↓
[ Spectral Feature Extraction (Welch's PSD -> MDF & MNF) ]
↓
[ Linear Regression & Fatigue Slope Quantification ]

---

## 🛠️ Built With
- **Python** 
- **SciPy** (Signal processing filters & linear regression)
- **NumPy** (Numerical arrays & spectral algorithms)
- **Matplotlib** (Time & frequency domain visualization)

---

## 🚀 Getting Started

### Prerequisites
Make sure you have Python 3.8+ installed. Install the necessary dependencies using `pip`:

```bash
pip install numpy scipy matplotlib

Running the Project
1. In Google Colab
Open your Colab notebook, copy the processing pipeline code into a code cell, and click Run.

2. Locally via Terminal
Clone the repository and run the Python script:

Bash
git clone [https://github.com/YOUR-USERNAME/semg-fatigue-analysis.git](https://github.com/YOUR-USERNAME/semg-fatigue-analysis.git)
cd semg-fatigue-analysis
python main.py

Metric,Start Baseline,Shift During Fatigue,Interpretation
MDF Slope,~120 Hz,"Negative (e.g., −4.5 Hz/s)",Muscle pitch drops over time
MNF Slope,~110 Hz,"Negative (e.g., −3.8 Hz/s)",Average spectral energy drops
Amplitude (RMS),Baseline,Increases,Motor units synchronize to maintain force
A negative slope ($m < 0$) in MDF or MNF serves as quantitative proof of muscle fatigue.

📜 License:
This mini-project is open source and available under the MIT License.
