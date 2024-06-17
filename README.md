# ImageDenoisingVLG
VLG Open Project

Open Project created by Soham Parolia, to enhance low light images.

The final trained model has been downloaded and below is the link to the same.
https://drive.google.com/drive/folders/1y4NVLE2aZqrHAGRV3awy20rTRuGVK1Wy?usp=sharing

## Table of Contents

- Introduction
- Dataset
- Models Used
- Results
- Installation
- Application
- References

## Introduction
![Alt text](https://user-images.githubusercontent.com/73076876/138980624-cbcf98bc-ac43-41a5-a399-5ca186858be0.png)

Light is of paramount importance to photography. Night and low light place very demanding constraints on photography due to very limited photon count and inescapable noise. One natural reaction is to gather more light by, e.g., enlarging aperture setting, lengthening exposure time and opening flashlight. However, each method brings a trade-off–large aperture incurs small depth of field, and is usually unavailable in smartphone cameras; long exposure can induce blur due to scene variations or camera motions; flash can cause color aberrations and is useful only for nearby objects. Therefore, denoising in extremely low-light conditions has become an important research direction in the low-level image processing community, aiming to restore details in images captured in extremely low-light scenes and enhance visual quality.

The project comprises of 3 main parts:
1. Data/Image Processing
2. Model Training and Prediction
3. Generating PSNR on comparing with original high-light images.

## Dataset

The dataset consisted of both high light and low light images in separate folders of around 482 images each, forming pairs used for training and validation. The dataset was roughly split 90%-10% as training set and validation set in the project. In some parts of the project (just for experimentation), I had used 3 random images from the dataset as the test data.

## Models Used

The main models used are:
1. UNET
2. DnCNN (Denoising Convolutional Neural Networks)
3. RCAN (Residual Channel Attention Network)

UNET: The model, originally developed for biomedical image segmentation, is an encoder-decoder network with skip connections that help preserve spatial information. The architecture makes it highly suitable for tasks requiring precise image reconstruction.
Encoder – consists of repeated applications of two 3x3 convolutions, each followed by a ReLU activation and a 2x2 max pooling operation.
Decoder – involves upsampling of feature maps, followed by a 2x2 up-convolution, concatenation with correspondingly cropped feature maps from the encoder, and two 3x3 convolutions followed by a ReLU activation.

DnCNN: It is an efficient deep learning model to estimate a residual image having the Gaussian noise. The underlying noise-free image can be estimated as the difference between the noisy image and the residue image. 

RCAN: They consist of a residual in residual (RIR) structure to form very deep network, which consists of several residual groups with long skip connections.

## Results

On applying the final UNET model to the entire training set, the final outcome was:
1. MSE: 0.0030771
2. PSNR: 26.078559875
3. MAE: 0.034

## Installation

Instructions on how to install this project.
```bash
git clone https://github.com/sohamparolia/ImageDenoisingVLG.git
```

## Application

Here are some potential uses of this project:
- Medical Imaging: Enhancing the quality of medical images like MRIs and CT scans.
- Satellite Imagery: Improving the resolution of satellite images for better analysis and interpretation.
- Photography: Enhancing the quality of photos taken in low-resolution settings.
- Surveillance: Improving the clarity of surveillance footage for better identification and monitoring.

## References
- https://arxiv.org/abs/1505.04597
- https://arxiv.org/abs/1608.03981
- https://arxiv.org/abs/1807.02758
