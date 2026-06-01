# 🩻 Chest X-Ray Disease Classification using DenseNet121

## Overview

This project focuses on automated chest X-ray disease classification using Deep Learning and Transfer Learning. The model is trained on a large-scale chest X-ray dataset from Kaggle and is capable of identifying multiple thoracic diseases from a single radiograph.

The implementation is built entirely in **PyTorch** and leverages a pretrained **DenseNet121** architecture. To improve model interpretability, **Grad-CAM heatmaps** are generated to visualize the regions of the X-ray that contribute most to the model's predictions.

---

## Project Highlights

✅ Multi-label chest X-ray disease classification

✅ Transfer Learning with pretrained DenseNet121

✅ PyTorch-based training pipeline

✅ Grad-CAM explainability visualizations

✅ Learning rate scheduling using ReduceLROnPlateau

✅ Achieved **83% ROC-AUC**, approaching the performance reported in the **ChestX-ray14 (CheXNet) paper**

✅ Trained on **NVIDIA Tesla T4 GPU** using Kaggle Notebooks

---

## Dataset

The model was trained on a chest X-ray dataset available on Kaggle containing frontal-view chest radiographs with disease labels.

The dataset includes multiple thoracic conditions such as:

* Atelectasis
* Cardiomegaly
* Consolidation
* Edema
* Effusion
* Emphysema
* Fibrosis
* Hernia
* Infiltration
* Mass
* Nodule
* Pleural Thickening
* Pneumonia
* Pneumothorax

This is a **multi-label classification problem**, meaning a single X-ray image can contain multiple diseases simultaneously.

---

## Model Architecture

### DenseNet121

This project uses a pretrained **DenseNet121** model initialized with ImageNet weights.

DenseNet (Densely Connected Convolutional Network) introduces direct connections between layers, allowing feature reuse throughout the network.

Key advantages include:

* Improved gradient flow
* Better feature propagation
* Reduced number of parameters
* Strong performance on medical imaging tasks

Instead of training from scratch, transfer learning allows the model to leverage visual features learned from millions of images and adapt them to chest X-ray classification.

The final classification layer was modified to output disease probabilities for all target classes.

---

## Training Configuration

| Component               | Value                      |
| ----------------------- | -------------------------- |
| Framework               | PyTorch                    |
| Backbone                | DenseNet121                |
| Loss Function           | BCEWithLogitsLoss          |
| Optimizer               | Adam                       |
| Learning Rate Scheduler | ReduceLROnPlateau          |
| Hardware                | NVIDIA Tesla T4 GPU        |
| Task Type               | Multi-label Classification |
| Evaluation Metric       | ROC-AUC                    |

---

## Why BCEWithLogitsLoss?

Since multiple diseases may appear in a single X-ray, this is not a standard multi-class problem.

`BCEWithLogitsLoss` combines:

* Sigmoid activation
* Binary Cross Entropy loss

into a numerically stable implementation that is well-suited for multi-label disease classification.

---

## Evaluation Metric

### ROC-AUC Score

Medical imaging datasets are often highly imbalanced.

Instead of relying solely on accuracy, the project uses **Area Under the Receiver Operating Characteristic Curve (ROC-AUC)** as the primary evaluation metric.

### Results

| Metric  | Score    |
| ------- | -------- |
| ROC-AUC | **0.83** |

The achieved ROC-AUC of **83%** is competitive and approaches the performance reported in the original **CheXNet** research.

---

## Explainable AI with Grad-CAM

To improve transparency and model interpretability, Grad-CAM heatmaps were generated.

Grad-CAM highlights image regions that most influenced the model's prediction, allowing visual verification that the model is focusing on clinically relevant areas of the chest X-ray.

### Sample Heatmaps

#### Original Chest X-Ray

<p align="center">
<img src="images/original_xray.png" width="700">
</p>

#### Grad-CAM Visualization

<p align="center">
<img src="images/gradcam_heatmap.png" width="700">
</p>

#### Overlay Comparison

<p align="center">
<img src="images/overlay.png" width="700">
</p>

---

## Technologies Used

* Python
* PyTorch
* Torchvision
* NumPy
* Pandas
* Matplotlib
* Scikit-Learn
* OpenCV
* Grad-CAM

---

## Key Learnings

Through this project, I gained practical experience in:

* Deep Learning for Medical Imaging
* Transfer Learning
* Multi-label Classification
* Model Explainability (XAI)
* ROC-AUC Evaluation
* PyTorch Training Pipelines
* Learning Rate Scheduling
* GPU-based Model Training

---

## Future Improvements

* Advanced data augmentation
* Cross-validation
* Ensemble models
* Vision Transformers (ViT)
* Model deployment with Gradio
* Clinical report generation using Vision-Language Models

---

## Acknowledgements

* CheXNet Research Team
* PyTorch Community
* Kaggle
* Stanford ChestX-ray14 Dataset Contributors

---

## Contact

If you would like to discuss this project, machine learning, medical AI, or potential collaboration opportunities, feel free to connect.
Checkout the Kaggle my notebook :https://www.kaggle.com/code/adityachaubeycode/densenet

⭐ If you found this project interesting, consider giving the repository a star.
Aditya chaubey 
