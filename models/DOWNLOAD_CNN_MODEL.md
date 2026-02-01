# Final CNN Model – PCOS Detection (EfficientNetB0)

The trained Convolutional Neural Network (CNN) model is too large to be stored directly on GitHub.

It has been uploaded to Google Drive and can be downloaded from the link below.

## 🔗 Download Link

https://drive.google.com/uc?id=1p2jdz_tdhTllysc50A4TqGqrWAipBV_Y&export=download

(File: `final_model.keras`)

---

## Model Details

- Architecture: EfficientNetB0 (ImageNet pre-trained)
- Task: Binary classification (Normal vs PCOS)
- Input size: 224 × 224 RGB ultrasound images
- Output: Sigmoid probability (PCOS likelihood)

## Performance (Test Set)

- AUC: ~0.98  
- Accuracy: ~0.80  

---

## How to Load the Model

```python
from tensorflow import keras

model = keras.models.load_model("final_model.keras")
