# 🧠 Transfer Learning-Based Multi-Disease Classification System for Retinal Fundus Images

> EfficientNet-B0 + Transfer Learning + Grad-CAM  
> Multi-Label Retinal Disease Classification (29 Classes)

---

## 📌 Project Overview

This project presents a deep learning-based multi-label retinal disease classification system built using EfficientNet-B0 in a transfer learning framework.

The system:

- Classifies retinal fundus images into 29 disease categories  
- Uses ImageNet-pretrained EfficientNet-B0  
- Applies fine-tuning for medical domain adaptation  
- Implements Grad-CAM for explainable AI  
- Achieves strong generalization performance (Test AUROC ≈ 0.8374)  

The objective is to combine efficient deep learning with clinical interpretability to support AI-assisted retinal diagnosis.

---

## 🏥 Dataset

Dataset Used: RFMiD (Retinal Fundus Multi-Disease Dataset)

- 29 retinal disease labels  
- Multi-label classification setup  
- Images resized to 224 × 224  
- Batch size: 16  
- Includes rare disease classes (AION, PT, RP, etc.)  

⚠️ The dataset is not included in this repository.

---

## 🧠 Model Architecture

### Backbone: EfficientNet-B0 (Pretrained on ImageNet)

Architecture components:

- Initial Conv 3×3 (stride 2)  
- 7 MBConv stages  
- Depthwise Separable Convolutions  
- Squeeze-and-Excitation blocks  
- Residual connections  
- Compound scaling (depth, width, resolution)  

The final classification layer is modified to output 29 classes for multi-label prediction.

---

## ⚙️ Training Configuration

Loss Function: Binary Cross Entropy with Logits  
Optimizer: Adam  
Scheduler: Learning Rate Scheduling  
Precision: Mixed Precision (AMP)  
Epochs: 20  
Batch Size: 16  
Input Size: 224×224  
Evaluation Metric: AUROC  

Model checkpointing is based on highest validation AUROC.

---

## 📊 Performance

### Validation Performance
- Best Validation AUROC: 0.8466  
- Validation Loss: ~0.1001  

### Test Performance
- Test AUROC: 0.8374  
- Test Loss: 0.0945  

The results indicate strong generalization across unseen retinal fundus images.

---

## 🔍 Explainability with Grad-CAM

Grad-CAM is used to:

- Visualize disease-relevant image regions  
- Highlight pathological attention areas  
- Improve transparency of model predictions  
- Support clinician trust in AI decisions  

---

## 🧪 Workflow Inside Notebook

   Load RFMiD dataset
   Apply data augmentation
   Initialize pretrained EfficientNet-B0
   Modify classification head (29 outputs)
   Enable mixed precision training
   Train model
   Track AUROC performance
   Save best model to saved_models/
   Generate Grad-CAM visualizations
---
## ⚠️ Limitations

   Class imbalance affects rare disease recall
   Lesion localization not quantitatively evaluated (IoU/Dice not measured)
   Requires further clinical validation before deployment
---
## 🔮 Future Improvements

  Focal Loss / Class-balanced Loss 
  Ensemble learning
  Quantitative localization metrics
  Convert notebook into modular production-ready code
  Clinical validation on diverse datasets
---
## 📚 References

- Tan & Le — EfficientNet
- Selvaraju et al. — Grad-CAM
- RFMiD Dataset Paper
- Deep Learning in Medical Imaging Surveys

---
## 👨‍💻 Authors
Dharsan K
P Keerthana
Sachin Pradeep
Department of Computer Science
SRM Institute of Science and Technology
