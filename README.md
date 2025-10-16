# Enhancing-Newborn-Health-Assessment- A Deep Learning U-Net Model for Newborn Body Composition Prediction
This repository contains the source files for the paper titled "Enhancing Newborn Health Assessment: Ultrasound-based Body Composition Prediction Using Deep Learning Techniques" published in the Ultrasound for Medicine &amp; Biology November 2025 edition. Read the full paper [here](https://www.sciencedirect.com/science/article/pii/S0301562925003813?dgcid=coauthor). For further inquiries, please contact rangerlabbc@gmail.com.

## Project Overview

This project presents a modified U-Net deep learning model for predicting newborn body composition, specifically fat mass (FM) and fat-free mass (FFM), from ultrasound images.

We implement and evaluate multiple deep learning and feature-based approaches, benchmarking their performance against traditional regression models such as HOG and SIFT. Model interpretability is enhanced through Grad-CAM, which highlights the image regions most influential in predictions.

Performance is assessed using the Mean Absolute Percentage Error (MAPE), with the proposed U-Net achieving a MAPE below 10%, demonstrating strong accuracy and reliability for ultrasound-based body composition prediction.

## Repository Structure: 
### U-NET Model: [UNet/](UNet/)
The U-Net Model and corresponding architecture are detailed in this repository. Linear layers are added to the traditional U-Net architecture to achieve a regression task. The ultrasound images are processed to be cropped and reshaped to be of Tensor type. The tensor channels are then passed through the model and trained using a 5-fold cross-validation technique. An independent test set is then used to create predictions. The ground truth and predictions are compared to generate a final MAPE score. Various augmentation and preprocessing techniques are also detailed in this section. 

### Grad-CAM: [Grad-CAM/](Grad-CAM/)
This folder contains visual interpretability materials supporting the paper's findings on model explainability:

- **`Grad-CAM/code/`**:  
  Includes a Jupyter notebook to recreate Grad-CAM heatmaps that highlight the regions within ultrasound images contributing most to fat mass (FM) and fat-free mass (FFM) predictions. The code applies Grad-CAM at the final layer of the U-Net model across abdomen, bicep, and quadriceps images.

- **`Grad-CAM/figures/`**:  
  Contains the final Grad-CAM visualization (**Figure 8** in the paper), which illustrates that the model emphasizes muscle tissue over subcutaneous fat, especially in the abdomen. These heatmaps provide insight into which anatomical features most influence the model's predictions.
  
### HOG & SIFT: [HOG and SIFT Regression/](HOG%20and%20SIFT%20Regression/)
Implements baseline feature-based models for performance comparison. Traditional regression techniques, particularly HOG and SIFT, are used to test the model performance in comparison to the U-Net model. MAPE statistics are generated again from these methods and compared to the corresponding U-Net model part predictions.

### Table & External Figures: [UMB_Tables&Figures/](UMB_Tables%26Figures/)
Contains the code and outputs used to generate Tables and Figures from the manuscript, including data summaries, performance comparisons, and visualization plots supporting the main results.

### Requirements: [requirements.txt](requirements.txt)
Lists all software dependencies.

### Data

This study used data from an observational cohort originally conducted at the **University of Minnesota Medical Center**, published in the *Journal of Parenteral and Enteral Nutrition* ([Nagel et al., 2021](https://aspenjournals.onlinelibrary.wiley.com/doi/10.1002/jpen.1829)).  

A secondary analysis was performed using ultrasound images and clinical data from that cohort, which enrolled 68 preterm infants born between 25–34 weeks gestation who were clinically stable (not requiring respiratory support or intravenous fluids). Ultrasound imaging of the arm, leg, and abdomen was performed alongside body composition measurements obtained using air displacement plethysmography (ADP). The post-menstrual age (PMA) at the time of measurement ranged from 32.6 to 38.7 weeks. For this secondary analysis, 65 infants with complete ultrasound and ADP data were included.  

A total of 721 B-mode ultrasound images were collected across three anatomical sites: the biceps (brachii & brachialis), abdomen (rectus abdominis), and quadriceps (rectus femoris & vastus intermedius) — using a NextGen LOGIQ e R7 ultrasound system (GE Medical Systems, Chicago, IL, USA). At least three images were acquired per region.  

All DICOM images were converted to JPEG format and underwent rigorous quality control, excluding scans with excessive acoustic shadowing, low tissue contrast, truncated views, or probe-induced compression. Each exclusion was reviewed independently by at least two researchers.   

Because the dataset contains identifiable neonatal ultrasound images, it remains **private and not publicly available**. Researchers interested in access should contact the study team via institutional collaboration.  

## Citation
If you use this repository or reference the study, please cite:

> He, K., Hohenberg, J., Li, Y., Xiao, A., Cho, H., Nagel, E., Ramel, S., Bell, K.A., Wei, D., Park, J., & Ranger, B.J. (2025).  
> *Enhancing Newborn Health Assessment: Ultrasound-based Body Composition Prediction Using Deep Learning Techniques.*  
> *Ultrasound in Medicine & Biology.* [https://www.sciencedirect.com/science/article/pii/S0301562925003813?dgcid=coauthor](https://www.sciencedirect.com/science/article/pii/S0301562925003813?dgcid=coauthor)

