# EEG-Based Brain-Computer Interface (BCI) Project  
Christine Gao – COGS 189  

---

## Project Overview

This project explores how EEG signals from motor imagery can be used to control a simple brain-computer interface (BCI).  

The goal is not only to classify EEG signals, but also to evaluate whether these predictions can support a **usable typing interface**.  

Two approaches are compared:
- Classical method: **CSP + LDA**
- Deep learning model: **EEGNet**

A simulated typing system is built to test how well model predictions translate into real control.

---

## Repository Structure

```
Project/
│
├── project.ipynb          # Main notebook (full pipeline + experiments)
├── report.pdf             # Final project report
├── README.md              # This file
│
└── data/
    ├── raw_control.gif        # Typing simulation (raw predictions)
    ├── confidence_control.gif # Typing simulation (confidence threshold)
    └── smoothed_control.gif   # Typing simulation (smoothed control)
```

---

## How to Run

1. Open `project.ipynb` in Jupyter / DataHub
2. Run all cells in order  
3. The notebook will:
   - Load EEG data
   - Preprocess signals (bandpass filtering, epoching)
   - Train models (CSP+LDA and EEGNet)
   - Evaluate performance
   - Run typing simulation
   - Generate plots and animations

---

## Methods Summary

- Dataset: **BCI Competition IV Dataset 2a**
- Channels: 22 EEG channels  
- Sampling rate: 250 Hz  
- Task: Left vs Right motor imagery  

### Preprocessing
- Bandpass filter: **8–30 Hz**
- Epochs: 0–4 seconds  

### Models
- **CSP + LDA** (classical baseline)
- **EEGNet** (deep learning model)

---

## Results Summary

- CSP + LDA achieves ~**81% accuracy**
- EEGNet achieves ~**61% accuracy** (limited data)

### Key Finding
Even with good classification accuracy, **raw predictions produce unstable control behavior**.

---

## Typing Simulation

The `data/` folder contains three animations showing system behavior:

- `raw_control.gif`  
  → Fast but unstable typing  

- `confidence_control.gif`  
  → Fewer errors, more controlled  

- `smoothed_control.gif`  
  → Most stable and usable behavior  

These demonstrate how post-processing improves real-world usability.

---

##  Key Insight

A usable BCI system requires:
- **Accurate models**
- **Stable control over time**

Improving classification alone is not sufficient.

---
