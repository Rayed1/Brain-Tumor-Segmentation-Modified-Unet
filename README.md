**Brain Tumor Segmentation with Modified U-Net Model**

This repository contains a deep learning-based pipeline for brain tumor segmentation using MRI images. The project utilizes a custom U-Net architecture with residual blocks for semantic segmentation, applied on the BraTS2020 dataset. The pipeline includes data preprocessing, model training, and evaluation with various metrics.

**Overview**

Brain tumor segmentation is a critical task in medical imaging to assist in diagnosis and treatment planning. This project focuses on:

*Segmenting MRI slices into four classes: Not Tumor, Necrotic/Core, Edema, and Enhancing Tumor.

*Using a custom U-Net model with residual blocks to improve feature representation and accuracy.

The pipeline processes MRI modalities (FLAIR, T1, T1CE, T2) along with ground truth segmentation masks and evaluates the model using metrics such as Dice Coefficient, Mean IoU, Precision, Sensitivity, and Specificity.

**Dataset**

This project uses the BraTS2020 dataset (Brain Tumor Segmentation Challenge 2020).

Dataset Features:

*Modality: Multimodal MRI scans (FLAIR, T1, T1CE, T2).

*Ground Truth: Segmentation masks with four labels:

  0: Not Tumor
  1: Necrotic/Core
  2: Edema
  3: Enhancing Tumor
  
*Structure: Data stored in .nii format.

Example Previews:
MRI Modalities: Visualizations of FLAIR, T1, T1CE, T2 slices.
Segmentation Mask: Corresponding annotated regions.

Data Split:
Training: 70%
Validation: 15%
Testing: 15%

**Model Architecture**

A custom U-Net architecture is implemented with:

*Residual Blocks for feature extraction.

*Downsampling and Upsampling paths with skip connections.

*Batch normalization and dropout for regularization.

*Final output layer with Softmax activation for multiclass segmentation.

Key Features:

*Input Shape: (128, 128, 2) (combined MRI modalities FLAIR and T1CE).

*Output: Probability maps for 4 classes.

**Training Pipeline**

1. Preprocessing:
   
  *Resize MRI slices to 128x128.
  
  *Normalize intensities and one-hot encode segmentation masks.
  
3. Data Generators:
   
  *Custom Keras generators for real-time data loading and augmentation.
  
5. Loss Function:
   
  *Combined Categorical Crossentropy and Dice Loss for improved performance.
  
7. Metrics:
   
  *Dice Coefficient, Mean IoU, Precision, Sensitivity, Specificity.
  
9. Callbacks:
    
  *Reduce learning rate on plateau.

**Evaluation**

The model is evaluated using:

1. Dice Coefficient: Measures overlap between predicted and ground truth segmentation.
2. Mean IoU: Intersection over Union for all classes.
3. Confusion Metrics: Precision, Sensitivity, Specificity.
