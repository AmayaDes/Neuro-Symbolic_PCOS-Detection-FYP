# Neuro-Symbolic PCOS Detection System  
Hybrid AI Pipeline for Interpretable Ultrasound Diagnosis

---

## Project Summary

This project implements a neuro-symbolic AI system for automated detection of Polycystic Ovary Syndrome (PCOS) from ovarian ultrasound images. The architecture integrates deep learning, symbolic reasoning, and explainability to produce accurate and interpretable predictions.

Rather than being a standalone ML experiment, the system is designed as a modular inference pipeline that separates feature extraction, neural prediction, rule-based reasoning, ensemble fusion, and explanation generation — mirroring real-world production AI workflows.

---

## System Architecture

```
========================================================
        Neuro-Symbolic PCOS Detection Architecture
========================================================

                ┌────────────────────┐
                │   User Interface   │
                │   (Streamlit UI)   │
                └─────────┬──────────┘
                          │ upload image
                          ▼
                ┌────────────────────┐
                │ Feature Extraction │
                │ blob + texture     │
                └─────────┬──────────┘
                          │ features
          ┌───────────────┴───────────────┐
          ▼                               ▼
┌───────────────────┐           ┌───────────────────┐
│    CNN Model      │           │ Decision Tree     │
│ EfficientNetB0    │           │ symbolic rules    │
└─────────┬─────────┘           └─────────┬─────────┘
          │ cnn score                     │ rule score
          └───────────────┬───────────────┘
                          ▼
                ┌────────────────────┐
                │     Ensemble       │
                │ score fusion       │
                └─────────┬──────────┘
                          │ prediction
                          ▼
                ┌────────────────────┐
                │  LIME Explainer    │
                │ interpretability   │
                └─────────┬──────────┘
                          ▼
                ┌────────────────────┐
                │ Final Result + UI  │
                └────────────────────┘

========================================================
```

The pipeline processes ultrasound images through modular components. Neural inference and symbolic reasoning operate independently and are combined through ensemble logic, with LIME providing interpretable explanations for predictions.

---

## Engineering Perspective

This system was built with architectural clarity and modularity in mind. Each component — preprocessing, feature extraction, neural classification, symbolic reasoning, ensemble fusion, and explanation — is implemented as an independent stage within a structured pipeline.

Key goals included:

- Separation of concerns across inference stages  
- Hybrid decision integration (neural + symbolic)  
- Reproducible data processing workflow  
- Explainability embedded in prediction flow  
- Clear system boundaries between backend logic and UI  

The structure reflects production-style AI system design rather than experimental notebook workflows.

---

## Dataset

The dataset was created by merging two public ultrasound datasets and applying preprocessing and deduplication steps to ensure consistency.

Sources:

- Kaggle PCOS ultrasound dataset  
- Roboflow PCOS dataset  

A processed train/validation/test split is hosted separately to support reproducibility.

---

## Pipeline Overview

1. Image preprocessing and deduplication  
2. Feature extraction (blob detection + texture analysis)  
3. CNN classification using EfficientNetB0  
4. Symbolic rule evaluation via decision tree  
5. Ensemble score fusion  
6. LIME explanation generation  
7. Visualization through Streamlit UI  

---

## Project Structure

```
Neuro-Symbolic-PCOS-Detection-FYP/
│
├── src/
│   ├── frontend/      Streamlit interface and visualization
│   └── backend/       Inference pipeline + ensemble logic
│
├── models/            Trained CNN and decision tree artifacts
├── notebooks/         Training and feature engineering workflows
├── results/           Evaluation outputs and metrics
├── demo.py            Terminal demonstration script
└── README.md
```

---

## Installation

### Requirements

- Python 3.9+
- TensorFlow
- OpenCV
- Streamlit
- scikit-learn
- lime
- pandas / numpy
- matplotlib / seaborn

Install dependencies:

```
pip install -r requirements.txt
```

---

## Running the Web Interface

```
cd Neuro-Symbolic-PCOS-Detection-FYP
streamlit run src/frontend/app.py
```

Upload an ultrasound image to receive prediction and explanation.

---

## Demo Mode (Terminal)

```
python demo.py
```

---

## Reproducibility

All experiments and model training steps can be reproduced by running notebooks in the `notebooks/` directory sequentially.

---

## Disclaimer

This system is a research prototype developed for academic purposes only.  
It is **not** a certified medical device and must not be used for clinical diagnosis.

---

