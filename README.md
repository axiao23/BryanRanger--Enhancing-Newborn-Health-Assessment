# Enhancing-Newborn-Health-Assessment: A Deep Learning U-Net Model for Newborn Body Composition Prediction
This repository contains the source files for the paper titled "Enhancing Newborn Health Assessment: Ultrasound-based Body Composition Prediction Using Deep Learning Techniques" published in *Ultrasound in Medicine &amp; Biology* (November 2025 edition). Read the full paper [here](https://www.sciencedirect.com/science/article/pii/S0301562925003813?dgcid=coauthor). For further inquiries, please contact rangerlabbc@gmail.com.

## Project Overview 

This project presents a modified U-Net deep learning model for predicting newborn body composition, specifically fat mass (FM) and fat-free mass (FFM), from ultrasound images.

We implement and evaluate multiple deep learning and feature-based approaches, benchmarking their performance against traditional regression models such as HOG and SIFT. Model interpretability is enhanced through Grad-CAM, which highlights the image regions most influential in predictions.

Performance is assessed using the Mean Absolute Percentage Error (MAPE), with the proposed U-Net achieving a MAPE below 10%, demonstrating strong accuracy and reliability for ultrasound-based body composition prediction.

## Repository Structure: 
### U-NET Model: 
[UNet/](UNet/)

The U-Net Model and corresponding architecture are detailed in this repository. Linear layers are added to the traditional U-Net architecture to achieve a regression task. Downsampling and upsampling layers are defined in the model. Ultrasound images are cropped, reshaped, and converted to tensor format. The tensor channels are then passed through the model and trained using a 5-fold cross-validation technique. An independent test set is then used to create predictions. The ground truth and predictions are compared to generate a final MAPE score. Various augmentation and preprocessing techniques are also detailed in this section. 

- **`UNet/code/`**:
  Includes a jupyter notebook which defines the architecture, methodology and the training of the UNet model propossed in our paper. The notebook also includes directory pathways to the dataset and ultrasound images utilized in the training of the model. The statistics used in Figure 2 and 3 in the paper are also generated and computed in the model.
- ** 'UNet/figures/'**  

### Grad-CAM: 
[Grad-CAM/](Grad-CAM/)

This folder contains visual interpretability materials supporting the paper's findings on model explainability:

- **`Grad-CAM/code/`**:  
  Includes a Jupyter notebook to recreate Grad-CAM heatmaps that highlight the regions within ultrasound images contributing most to fat mass (FM) and fat-free mass (FFM) predictions. The code applies Grad-CAM at the final layer of the U-Net model across abdomen, bicep, and quadriceps images.

- **`Grad-CAM/figures/`**:  
  Contains the final Grad-CAM visualization (**Figure 8** in the paper), which illustrates that the model emphasizes muscle tissue over subcutaneous fat, especially in the abdomen. These heatmaps provide insight into which anatomical features most influence the model's predictions.
  
### HOG & SIFT: 
[HOG and SIFT Regression/](HOG%20and%20SIFT%20Regression/)

Implements baseline feature-based regression models for performance comparison. HOG and SIFT features are extracted from ultrasound images and used to predict body composition. MAPE metrics from these traditional models are compared directly with the U-Net predictions and are detailed in Figuure 3. 

### Table & External Figures: 
[UMB_Tables&Figures/](UMB_Tables%26Figures/)

Contains the code and outputs used to generate Tables and Figures from the manuscript, including model performance summaries and Bland–Altman analyses supporting the main results.

### Requirements: 
[requirements.txt](requirements.txt)

Lists all software dependencies.

### Data:
[UltrasoundData.txt](UltrasoundData.txt)

All details about the dataset, imaging protocol, and preprocessing steps are provided in **UltrasoundData.txt**. 

This study used data from an observational cohort originally conducted at the **University of Minnesota Medical Center**, published in the *Journal of Parenteral and Enteral Nutrition* ([Nagel et al., 2021](https://aspenjournals.onlinelibrary.wiley.com/doi/10.1002/jpen.1829)).  

Because the dataset contains identifiable neonatal ultrasound images, it remains **private and not publicly available**. Researchers interested in access should contact the study team via institutional collaboration.

## Citation

If you use this repository or reference the study, please cite:

> **Keshi He, Julia Hohenberg, Yi Li, Audrey Xiao, Hayoung Cho, Emily Nagel, Sara Ramel, Katherine A. Bell, Donglai Wei, Jinhee Park, Bryan J. Ranger.**  
> *Enhancing Newborn Health Assessment: Ultrasound-based Body Composition Prediction Using Deep Learning Techniques.*  
> *Ultrasound in Medicine & Biology*, 2025. ISSN 0301-5629.  
> [https://doi.org/10.1016/j.ultrasmedbio.2025.09.016](https://doi.org/10.1016/j.ultrasmedbio.2025.09.016)  
> [Available online at ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0301562925003813)
