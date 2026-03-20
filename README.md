# Sensorimotor ERD EEG Analysis

**Decoding Motor Intent from Sensorimotor Oscillations Using Time-Frequency EEG Analysis**

## Overview

This project investigates how motor intent can be detected from scalp electroencephalography (EEG) signals using signal processing techniques commonly used in brain–computer interface (BCI) research.

During voluntary movement, oscillatory activity in the sensorimotor cortex exhibits characteristic decreases in power within the **mu (8–12 Hz)** and **beta (13–30 Hz)** frequency bands. This phenomenon, known as **event-related desynchronization (ERD)**, reflects neural activation associated with motor planning and execution.

The goal of this project is to identify and quantify ERD patterns from EEG recordings and evaluate whether spectral features of sensorimotor rhythms can reliably distinguish **rest vs movement states**.

---

## Research Question

Can motor preparation and movement execution be detected from spectral EEG features in the mu and beta frequency bands over the sensorimotor cortex?

---

## Key Concepts

* **Sensorimotor Rhythms (SMR)** – Oscillatory activity over motor cortex
* **Mu Rhythm (8–12 Hz)** – Associated with motor planning and imagery
* **Beta Rhythm (13–30 Hz)** – Associated with motor execution
* **Event-Related Desynchronization (ERD)** – Decrease in oscillatory power during movement
* **Time–Frequency Analysis** – Reveals dynamic spectral changes during motor tasks

---

## Dataset

This project uses the **EEG Motor Movement/Imagery Dataset** from PhysioNet.

Dataset link:
https://physionet.org/content/eegmmidb/

Dataset characteristics:

* 109 subjects
* 64-channel EEG recordings
* Motor movement and motor imagery tasks
* Sampling rate: 160 Hz

Tasks include:

* Left hand movement
* Right hand movement
* Both fists movement
* Both feet movement
* Rest baseline

---

## Methods

### EEG Preprocessing

* Channel selection (C3, Cz, C4)
* Bandpass filtering (1–40 Hz)
* Trial segmentation around movement onset

### Spectral Analysis

Power spectral density (PSD) is estimated using **Welch’s method** to compare oscillatory power across conditions.

### Time–Frequency Analysis

Short-Time Fourier Transform (STFT) or wavelet transforms are used to visualize changes in oscillatory power across time.

### Event-Related Desynchronization (ERD)

ERD is calculated by comparing baseline power to task power:

ERD (%) = ((Baseline Power − Task Power) / Baseline Power) × 100

This quantifies the suppression of mu and beta rhythms during movement.

---

## Visualization Outputs

The analysis produces several visualizations:

* Raw EEG signal examples
* Power spectral density comparisons
* Time–frequency spectrograms
* Event-related desynchronization plots

Example analyses focus on electrodes over the **sensorimotor cortex**:

* **C3**
* **Cz**
* **C4**

---

## Project Structure

```
sensorimotor-erd-eeg-analysis
│
├── sensorimotor_eeg_analysis.ipynb
├── README.md
├── figures/
│   ├── psd_plot.png
│   ├── spectrogram.png
│   └── erd_plot.png
└── requirements.txt
```

---

## Tools & Libraries

Python libraries used in this project include:

* NumPy
* SciPy
* Matplotlib
* MNE-Python
* Scikit-learn (optional for classification)

---

## Reproducibility

To reproduce the analysis:

1. Clone the repository

```
git clone https://github.com/keeratkaurt/sensorimotor-erd-eeg-analysis.git
```

2. Install dependencies

```
pip install -r requirements.txt
```

3. Open the notebook

```
jupyter notebook sensorimotor_eeg_analysis.ipynb
```

---

## Applications

Understanding neural markers of motor intent has important applications in:

* Brain–computer interfaces (BCIs)
* Neuroprosthetics
* Rehabilitation engineering
* Assistive technologies for motor impairments

---

## Future Work

Possible extensions of this project include:

* Training classifiers to decode motor intent
* Comparing ERD across subjects
* Investigating spatial filtering methods such as Common Spatial Patterns (CSP)
* Applying deep learning models to EEG time–frequency representations

---

## Authors

Keerat Kaur
Cognitive Science – Machine Learning & Neural Computation   
University of California, San Diego

Nicolas Thiele
Cognitive Science – Neuroscience   
University of California, San Diego

Alexander Jacobo
Cognitive Science – Machine Learning & Neural Computation   
University of California, San Diego

---

## License

This project is released under the MIT License.
