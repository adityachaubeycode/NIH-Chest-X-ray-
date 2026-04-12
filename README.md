🫁 NIH Chest X-ray Classification using DenseNet

This NIH Chest X-ray Dataset is comprised of 112,120 X-ray images with disease labels from 30,805 unique patients. To create these labels, the authors used Natural Language Processing to text-mine disease classifications from the associated radiological reports. The labels are expected to be >90% accurate and suitable for weakly-supervised learning. The original radiology reports are not publicly available but you can find more details on the labeling process in this Open Access paper: "ChestX-ray8: Hospital-scale Chest X-ray Database and Benchmarks on Weakly-Supervised Classification and Localization of Common Thorax Diseases." (Wang et al.)

<img width="685" height="692" alt="image" src="https://github.com/user-attachments/assets/ae1a9092-46c9-473f-aea3-3201cd06cca3" />

📌 Abstract

This project focuses on automated thoracic disease classification using chest X-ray images from the NIH dataset. Leveraging deep learning techniques, specifically a DenseNet-based architecture, the model aims to learn high-level visual representations for multi-label classification of chest pathologies. The work is inspired by recent advances in medical imaging and seeks to improve diagnostic assistance using convolutional neural networks.

📂 Dataset
Dataset Name: NIH Chest X-ray Dataset (ChestX-ray14)
Source: Kaggle
Link: (https://www.kaggle.com/datasets/nih-chest-xrays/data)
Dataset Description
📊 Key Highlights
🔬 Medical Imaging Use Case – Real-world dataset (NIH ChestX-ray14)
🧠 Model – DenseNet (transfer learning + fine-tuning)
⚖️ Multi-label Classification – 14 thoracic diseases
🧪 Augmentation – Albumentations pipeline
📈 Evaluation – AUROC, F1-score, Precision/Recall
⚡ Efficient Training – PyTorch + tqdm + timeit
📂 Dataset
Name: NIH Chest X-ray Dataset (ChestX-ray14)
Source: Kaggle
Link: (Paste your dataset link here)
📌 Dataset Summary
~100,000+ frontal chest X-ray images
14 disease labels (multi-label classification)
Real-world noisy annotations
Highly imbalanced class distribution
🏷️ Disease Labels

<img width="685" height="381" alt="image" src="https://github.com/user-attachments/assets/90ff2529-d179-498c-ba37-b8f19d536ea8" />


The NIH Chest X-ray dataset contains over 100,000 frontal-view X-ray images annotated with 14 disease labels, including:

Atelectasis
Cardiomegaly
Effusion
Infiltration
Mass
Nodule
Pneumonia
Pneumothorax
Consolidation
Edema
Emphysema
Fibrosis
Pleural Thickening
Hernia
Key Characteristics
Multi-label classification problem
High class imbalance
Grayscale medical images
Resolution varies (commonly resized during preprocessing)
⚙️ Libraries & Tools

The following libraries were used in the implementation:

PyTorch – Deep learning framework
tqdm – Progress tracking
timeit – Performance benchmarking
matplotlib – Visualization
pandas – Data handling
albumentations – Data augmentation
🧠 Methodology
Model Architecture
Backbone: DenseNet (pretrained)
Fine-tuned on NIH dataset
Adapted final fully connected layer for multi-label classification
Why DenseNet?

DenseNet improves feature propagation and reduces vanishing gradients through dense connectivity, making it particularly effective for medical imaging tasks.

🔄 Data Preprocessing
Image resizing (e.g., 224×224)
Normalization
Data augmentation using albumentations:
Horizontal flipping
Random brightness/contrast
Rotation
🏋️ Training Details
Loss Function: Binary Cross Entropy (BCE) / BCEWithLogitsLoss
Optimizer: Adam
Learning Rate: Tuned experimentally
Batch Size: Depends on GPU capacity
Epochs: (Specify your number)
Training Strategy
Transfer learning with pretrained weights
Fine-tuning deeper layers
Monitoring validation loss to prevent overfitting
📊 Evaluation Metrics
Accuracy
AUROC (Area Under ROC Curve)
F1 Score
Precision / Recall

Example:

Mean AUROC: 50
Best performing class: Pneumonia
Observations:
Model performs well on high-frequency classes
Struggles with rare pathologies due to imbalance

🚀 How to Run

# Clone repository
git clone <your-repo-link>

# Install dependencies
pip install -r requirements.txt

# Run training
python train.py

# Evaluate model
python evaluate.py

⚠️ Challenges
Severe class imbalance
Noisy labels in dataset
High intra-class similarity
Limited interpretability of predictions

🔮 Future Work
Incorporate attention mechanisms (e.g., Grad-CAM visualization)
Use ensemble models
Apply class balancing techniques (e.g., focal loss)
Experiment with Vision Transformers

📚 References
NIH Chest X-ray Dataset paper
DenseNet Architecture Paper
Recent medical imaging research papers


🚀 Project Overview

This project implements a deep learning pipeline for multi-label thoracic disease classification using chest X-ray images from the NIH dataset. The model is built on a DenseNet backbone and optimized for handling class imbalance and multi-label prediction challenges common in medical imaging.

The goal is to simulate a real-world clinical decision support system, where multiple pathologies may co-exist in a single radiograph.

👨‍💻 Author
Aditya Chaubey 
DL Enthusiastic
Focus: Deep Learning, Medical Imaging, AI Systems
⭐ If You Found This Useful
Give it a star ⭐ on GitHub — it helps visibility and motivates further development.
