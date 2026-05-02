---

# 🧠 EEG Seizure Detection using ML, CNN, Transfer Learning & XAI

## 📌 Overview

This project implements a **complete EEG classification pipeline** for epileptic seizure detection using:

* Machine Learning (SVM, Random Forest)
* Deep Learning (CNN on spectrograms)
* Transfer Learning (ResNet50)
* Explainable AI (Grad-CAM)

👉 Final performance reaches **~99% accuracy with interpretability**

---

# 📂 Repository File Guide (IMPORTANT)

> ⚠️ All main code files are present in the **root directory itself**.
> Each file corresponds to a specific phase of the project.

---

## 🔹 Spectrogram Generation

```text id="f0r8a3"
<spectrograms.ipynb>
```

### Purpose:

* Converts EEG `.txt` signals → spectrogram images
* Uses STFT + log scaling

👉 Output:

```text id="x3gq6l"
spectrogram_dataset/
    healthy/
    ictal/
    interictal/
```

---

## 🔹 Phase 1 – Machine Learning

```text id="h0z7ne"
<Feature_Extraction/feature_extraction.py>
```

### Contains:

* Signal preprocessing (bandpass filtering)
* Sub-band decomposition
* Feature extraction:

  * Statistical
  * Spectral
  * Entropy

👉 Generates:

```text id="i1v3o9"
EEG_Feature_Dataset.csv
```


### Contains:

* SVM (RBF)
* Random Forest
* Feature selection

👉 Output:

* Accuracy scores
* Classification report

---

## 🔹 Phase 2 – CNN (Spectrogram Classification)

```text id="n3w8kp"
<customCNN.ipynb>
```

### Contains:

* Data loading using ImageDataGenerator
* Normalization (mean/std)
* Custom CNN architecture
* Ablation study variants

👉 Output:

* Model accuracy
* Training curves

---

## 🔹 Phase 3 – Transfer Learning

```text id="b6t2xm"
<EEG_detection_Resnet_XAI.ipynb>
```

### Contains:

* ResNet50 (ImageNet pretrained)
* Fine-tuning
* Custom classification head

👉 Output:

* Test accuracy (~98–99%)
* Confusion matrix

---

## 🔹 Explainable AI (Grad-CAM)

```text id="v4rq2c"
<EEG_detection_Resnet_XAI.ipynb>
```

### Contains:

* Feature map extraction
* Gradient computation
* Heatmap generation

👉 Output:

* Grad-CAM overlay images

---

## 📁 Results Folder

```text id="rfmzpk"
Results/
```

### Contains:

* Confusion matrices
* Accuracy plots
* Grad-CAM outputs
* Model comparison visuals

👉 This is the **best place to understand model performance quickly**

---

# ▶️ Execution Flow (VERY IMPORTANT)

Follow this order to reproduce the project:

```text id="b4v9tl"
1. Run spectrogram generation file
2. Run Phase 1 (feature extraction + ML)
3. Run Phase 2 (CNN training)
4. Run Phase 3 (transfer learning)
5. Run Grad-CAM for visualization
```

---

# 🔬 Methodology Summary

```text id="p2j4hc"
EEG → Preprocessing → 
    ├── Feature Extraction → ML (SVM, RF)
    ├── Spectrogram → CNN
    └── Transfer Learning (ResNet50) → Grad-CAM
```
#Main files are organized based on project phases:

Phase 1 (Machine Learning):
- Feature extraction and ML models (SVM, Random Forest)

Phase 2 (CNN):
- Spectrogram generation and CNN training

Phase 3 (Transfer Learning + XAI):
- ResNet50 model and Grad-CAM visualization

Results:
- Contains outputs, confusion matrices, and Grad-CAM images

---

# 📊 Results Summary

| Model         | Accuracy   | Notes                 |
| ------------- | ---------- | --------------------- |
| SVM           | 94%        | Baseline              |
| Random Forest | 97%        | Best ML model         |
| CNN (Dropout) | 98%        | Strong generalization |
| ResNet50      | **98–99%** | Best overall          |
| EfficientNet  | 68%        | Poor adaptation       |
| GoogleNet     | 89%        | Not Good Enough       |
---

# 🔍 Explainability (Grad-CAM)

Grad-CAM visualizations show:

* Healthy → stable patterns
* Ictal → high-energy spikes
* Interictal → mixed patterns

👉 Confirms model focuses on **meaningful EEG regions**

---

# 🧠 Key Contributions

* End-to-end EEG classification pipeline
* Comparison: ML vs CNN vs Transfer Learning
* High accuracy (~99%)
* Explainable AI integration

---

# ⚠️ Notes

* Code is organized **phase-wise logically**, not folder-wise
* Results are available in the **Results folder**
* Each file corresponds to a specific stage

---
## 🧠 Key Insights

* Feature-based Machine Learning provides a strong baseline for EEG classification
* CNN models eliminate the need for manual feature extraction
* Transfer learning improves generalization and reduces training complexity
* Explainable AI (Grad-CAM) enhances model interpretability and trustworthiness

---

## ⚠️ Limitations

* Dataset size is limited (Bonn EEG dataset)
* No temporal sequence modeling (e.g., LSTM or Transformers not used)
* No real-time deployment or streaming EEG analysis

---

## 🔮 Future Work

* Hybrid CNN + LSTM or Transformer-based architectures for temporal learning
* Real-time EEG seizure detection system
* Evaluation on large multi-patient clinical datasets
* Clinical validation for hospital deployment

---

## 🛠️ Technologies Used

* Python
* NumPy, SciPy
* Matplotlib
* Scikit-learn
* TensorFlow / Keras

---

## ▶️ How to Run

1. Generate spectrogram dataset from EEG signals
2. Train Phase 1: Machine Learning models (SVM, Random Forest)
3. Train Phase 2: CNN model on spectrogram images
4. Train Phase 3: Transfer Learning (ResNet50 fine-tuning)
5. Apply Grad-CAM for model explainability and visualization

---

## 📌 Conclusion

This project presents a complete EEG-based seizure detection pipeline combining:

* Machine Learning
* Deep Learning
* Transfer Learning
* Explainable AI (XAI)

The proposed system achieves high classification accuracy (~99%) while maintaining interpretability, making it suitable for real-world medical AI applications.

---

