# Neuro-Symbolic-PCOS-Detection-FYP  
PCOS Detection Using Ultrasound Images

## Project Overview  
This project presents a neuro-symbolic AI system for automated detection of Polycystic Ovary Syndrome (PCOS) from ovarian ultrasound images.  
The system integrates deep learning (CNN), symbolic rule-based reasoning, and LIME explainability to provide both accurate predictions and clinically interpretable outputs.

---

## Dataset  
The dataset was created by merging two public datasets:

Kaggle: https://www.kaggle.com/datasets/anaghachoudhari/pcos-detection-using-ultrasound-images  
Roboflow: https://universe.roboflow.com/pcos-a0bjy/pcos-te6mi  

The processed dataset (train/validation/test split) is hosted on Kaggle:  
https://www.kaggle.com/datasets/amayajayarathna/pcos-ultrasound-dataset-trainvaltest-split  

---

## System Pipeline  
1. Data preparation and deduplication  
2. Feature extraction (blob detection + texture features)  
3. Rule extraction using decision tree  
4. CNN training using EfficientNetB0  
5. Ensemble prediction (CNN + Rules)  
6. LIME-based explainability  
7. Visualization through Streamlit UI  

---

## Requirements  
Python 3.9+  
TensorFlow  
OpenCV  
Streamlit  
scikit-learn  
lime  
joblib  
matplotlib  
seaborn  
pandas  
numpy  

Install all dependencies using:     pip install -r requirements.txt  

---

## Project Structure  

Neuro-Symbolic-PCOS-Detection-FYP/  
├── src/  
│   ├── frontend/       Streamlit UI  
│   └── backend/        PCOSProductionSystem (CNN + Rules + LIME)  
│  
├── models/             Trained CNN + Decision Tree  
├── notebooks/          Training and feature extraction  
├── results/            Evaluation outputs  
├── demo.py             Terminal-based demo  
└── README.md  

---

## How to Run (Web Interface)

1. Go inside the folder
cd Neuro-Symbolic-PCOS-Detection-FYP  

2. Install dependencies:

pip install -r requirements.txt  

3. Run the Streamlit application:

streamlit run src/frontend/app.py  

4. Open the browser and upload an ultrasound image to receive prediction and explanation.

---

## Demo Mode (Terminal)

To run without the web interface:

python demo.py  

---

## Reproducibility  
All experiments can be reproduced by running the notebooks in the notebooks folder in order.

---

## Disclaimer  
This system is a research prototype developed for academic purposes only.  
It is not a certified medical device and must not be used for clinical diagnosis.  
All outputs should be interpreted by a qualified medical professional.
