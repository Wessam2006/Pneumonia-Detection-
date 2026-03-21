🫁 Pneumonia Detection from Chest X-Rays
An AI-driven medical imaging project that classifies chest X-ray images into Normal or Pneumonia categories. This system utilizes Deep Learning (CNNs) and Transfer Learning to provide rapid screening and clinical decision support.

##  Project Goal
The primary objective is to build an automated diagnostic tool that distinguishes between healthy lungs and those affected by pneumonia. This acts as a first-pass screening tool to assist radiologists, especially in regions with limited medical resources.
##  Technical Workflow### 1. Dataset & PreparationData Split: Organized into Train, Validation, and Test sets to ensure unbiased evaluation.Preprocessing: Images resized to $224 \times 224$ pixels and normalized.Augmentation: Random flips, rotations, and brightness adjustments are applied to training data to improve model generalization.Handling Imbalance: Utilized a WeightedRandomSampler to ensure the model doesn't become biased toward the more frequent Pneumonia class.
Gemini said
This is a fantastic breakdown. As a Biomedical Engineering student, highlighting Grad-CAM Explainability and Class Imbalance Handling is key—it shows you understand the clinical risks of "black box" AI and biased datasets.

Below is a professional README.md for your Pneumonia Detection project. You can paste this directly into your repository.

🫁 Pneumonia Detection from Chest X-Rays
An AI-driven medical imaging project that classifies chest X-ray images into Normal or Pneumonia categories. This system utilizes Deep Learning (CNNs) and Transfer Learning to provide rapid screening and clinical decision support.

##  Project Goal
The primary objective is to build an automated diagnostic tool that distinguishes between healthy lungs and those affected by pneumonia. This acts as a first-pass screening tool to assist radiologists, especially in regions with limited medical resources.

##  Technical Workflow
### 1. Dataset & Preparation
Data Split: Organized into Train, Validation, and Test sets to ensure unbiased evaluation.

Preprocessing: Images resized to 224×224 pixels and normalized.

Augmentation: Random flips, rotations, and brightness adjustments are applied to training data to improve model generalization.

Handling Imbalance: Utilized a WeightedRandomSampler to ensure the model doesn't become biased toward the more frequent Pneumonia class.

### 2. Model Architecture: Transfer Learning
The project employs ResNet-18, pre-trained on ImageNet, to leverage existing knowledge of shapes and textures:

Phase 1 (Feature Extraction): The ResNet backbone is frozen; only the final fully connected layer is trained.

Phase 2 (Fine-Tuning): The entire network is unfrozen and trained at a very low learning rate to specialize in medical imaging features.

### 3. Training Strategy
Optimization: Weights are adjusted over 15 epochs based on loss calculations.

Early Stopping: Monitoring validation loss to prevent overfitting.

Checkpointing: Automatically saves the best-performing model based on validation metrics.
## 📊 Evaluation & Explainability
### Performance Metrics
The model is evaluated using standard clinical metrics:

Accuracy: Overall correctness.

Precision & Recall: Critical for ensuring we don't miss actual pneumonia cases (High Recall).

F1-Score: The harmonic mean of precision and recall.

ROC-AUC: Measures the model's ability to distinguish between classes.

### Grad-CAM (Explainability)
To move beyond a "black box," this project implements Grad-CAM. It produces a heatmap overlaid on the X-ray to show exactly which regions the AI focused on.

Red Areas: High influence on the decision.

Validation: Ensures the model is identifying lung pathologies rather than irrelevant artifacts.
##  How to Use
Open the Notebook:

Run All Cells: The notebook will automatically download the dataset (if linked) or prompt for upload.

View Heatmaps: Check the "Sample Predictions" section to see Grad-CAM results on test images.

## Clinical Significance
Pneumonia remains a leading cause of mortality worldwide, particularly among children. This AI tool provides:

Consistency: Removes human fatigue from the screening process.

Speed: Near-instantaneous results available 24/7.

Scalability: Can be deployed in rural clinics where radiologists are scarce.
