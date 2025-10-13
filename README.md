# Enhancing-Newborn-Health-Assessment- A Deep Learning UNet Model for Newborn Body Composition Prediction
This repository contains the source files for the paper titled "Enhancing Newborn Health Assessment: Ultrasound-based Body Composition Prediction Using Deep Learning Techniques" published in the Ultrasound for Medicine &amp; Biology November 2025 edition. For further inquires, please contact rangerlabbc@gmail.com

## Project Overview

This project explores a U-Net Shaped deep learning–based model for predicting newborn body composition, specifically fat-mass and fat-free mass using ultrasound imaging.
We implement and evaluate multiple approaches in comparsion to UNet segmentation and interpret the results using Grad-CAM explainability. The model's performance is compared against traditional regression models such as HOG and SIFT regression. The metric Mean Absolute Percentage Error or (MAPE) is used to assess the model performance. Our model achieves a MAPE score of less than 10%, proving to be effective in predicting body composition.

## Repository Structure: 
### UNET Model audrey
The UNet Model and corresponding architecture is detailed in this repository. Linear layers are added to the traditional UNet architecture to achieve a regression task. The ultrasound images are processed to be cropped and reshpaed to be of Tensor type. The tensor channels are then passed through the model and trained using a 5-fold cross validation technique. An independent test set is then used to create predictions. The ground truth and predictions are compared to generate a final MAPE score. Various augmentation and preprocessing techiques are also detailed in this section. 

### GradCam julie
This folder contains visual interpretability materials supporting the paper's findings on model explainability:

- **`Grad-CAM/code/`**:  
  Includes a Jupyter notebook to recreate Grad-CAM heatmaps that highlight the regions within ultrasound images contributing most to fat mass (FM) and fat-free mass (FFM) predictions. The code applies Grad-CAM at the final layer of the U-Net model across abdomen, bicep, and quadriceps images.

- **`Grad-CAM/figures/`**:  
  Contains the final Grad-CAM visualization (**Figure 8** in the paper), which illustrates that the model emphasizes muscle tissue over subcutaneous fat, especially in the abdomen. These heatmaps provide insight into which anatomical features most influence the model's predictions.
  
### HOG & SIFT audrey
- Traditional regression tecniques, particularly HOG and SIFT are used to test the model performance in comparison the the UNEt model. MAPE statistics are generated again from these methods and compared to corresponding UNet model part predictions.

### Table & External Figures audrey
This section gives 

### Requirements txt audrey
 

### Data (explanation) 

*the data is collected from a private 
