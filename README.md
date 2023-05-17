# Deep learning for identification of pure seminoma subtypes using H&E slides

This repository provides pretrained model for identification of pure seminoma subtypes. Seminoma subtypes were identified using data from The Cancer Genome Atlas (https://portal.gdc.cancer.gov/) [https://doi.org/10.1101/2022.04.25.489437].

Overview of dataset preparation, training and validation process:

<img width="450" alt="изображение" src="https://user-images.githubusercontent.com/95879893/167447521-6b29153e-2596-4931-9a10-af597747da6e.png">


For training this model we used all histopathological slides available at TCGA data portal for 64 pure seminoma samples (156 slides). Pure seminoma regions of interest (ROIs) were assigned and verified for each slide. Verified ROIs were subsequently split into smaller tiles (300x300 pixels) at 20X magnification and with 50% overlap. Models training was performed for 40 epochs.

Model was trained using:
- Tensorflow 2.5.0
- CUDA 11.2 
- cuDNN 8.1
- Binary Cross Entropy loss function
- Adam optimizer 
- Inception-v3 architecture [https://arxiv.org/abs/1512.00567]

At the validation step model achieved the highest accuracy with 0.933.
Area under the ROC curve for validation = 0.92

![изображение](https://user-images.githubusercontent.com/95879893/167448397-e625b17c-fa6d-487f-b0fe-7e4bb245d7a9.png)

## Usage

```python
import tensorflow as tf
model = tf.keras.models.load_model('./seminoma_subtypes_model.h5')
```

## References
1. Medvedev KE, Savelyeva AV, Chen KS, Bagrodia A, Jia L, Grishin NV. Integrated Molecular Analysis Reveals 2 Distinct Subtypes of Pure Seminoma of the Testis. _Cancer Informstics_. 2022, 21. https://doi.org/10.1177/11769351221132634
2. Medvedev KE, Savelyeva AV. Seminoma subtypes differ in the organization and functional state of the immune microenvironment. _3 Biotech_. 2023, 13(3):110. https://doi.org/10.1007/s13205-023-03530-1
3. Medvedev KE, Jia L, Rajaram S, Grishin NV. Deep learning for subtypes identification of pure seminoma of the testis. 

