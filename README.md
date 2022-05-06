# Deep learning for identification of pure seminoma subtypes using H&E slides

This repository provides pretrained model for identification of pure seminoma subtypes. Seminoma subtypes were identified using samples from The Cancer Genome Atlas (https://portal.gdc.cancer.gov/) [https://doi.org/10.1101/2022.04.25.489437].

For training this model we used all histopathological slides available at TCGA data portal for 64 pure seminoma samples (156 slides). Pure seminoma regions of interest (ROIs) were assigned and verified for each slide. Verified ROIs were subsequently split into smaller tiles (300x300 pixels) at 20X magnification and with 50% overlap.

Model was trained using:
- Tensorflow 2.5.0
- CUDA 11.2 
- cuDNN 8.1
- Binary Cross Entropy loss function
- Adam optimizer 
- Inception-v3 architecture
