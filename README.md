# Retinal Blood Vessel Segmentation using Unet (Pytorch) - Post Morphological Enhancements

This repository contains the code for semantic segmentation of the retina blood vessel on the DRIVE dataset using the PyTorch framework. 


# Files

Contains IPYNB - 
1) Data augmentation
2) Training
3) Testing

Python .py files - 
1) Model
2) Loss
3) Utils
4) data

Readme.md

##  Folders

Results
New_data - contains augmented Test Train Dataset
files - saves the checkpoint 

## Unet

![](https://nchlis.github.io/2019_10_30/architecture_unetV2.png)
Deep Learning has enabled the field of Computer Vision to advance rapidly in the last few years.  One specific task in Computer Vision called as **Semantic Segmentation**.

Given an input image, the goal of a segmentation method is to predict a segmentation mask that highlights an obect (or objects) of interest. This segmentation mask typically corresponds to a binary image of the same size as the input where pixels equal to one correspond to foreground (object) pixels and pixels equal to zero correspond to background pixels


## DRIVE DataSet

DRIVE: Digital Retinal Images for Vessel Extraction
 The DRIVE database has been established to enable comparative studies on segmentation of blood vessels in retinal images. Retinal vessel segmentation and delineation of morphological attributes of retinal blood vessels, such as length, width, tortuosity, branching patterns and angles are utilized for the diagnosis, screening, treatment, and evaluation of various cardiovascular and ophthalmologic diseases such as diabetes, hypertension, arteriosclerosis and chorodial neovascularization

The photographs for the DRIVE database were obtained from a diabetic retinopathy screening program in The Netherlands
The set of 40 images has been divided into a training and a test set, both containing 20 images.
[DRIVE Dataset](https://drive.grand-challenge.org/)

![21_training](https://user-images.githubusercontent.com/78692554/126083644-9e7c866c-62fe-4000-bbe4-b11ba82e554b.jpg)
![21_training](https://user-images.githubusercontent.com/78692554/126083650-e93ebf41-5ca8-433f-8671-cee14cfd75c8.jpg)


# Inplementaion

The DRIVE dataset has 20 Training samples which is less than that is required for Training an Unet, hence initially augmentation of the dataset is carried out  which creates a total of 100 images including the original one of size 512 x 512

This data is feeded for Unet model for training and further testing, the details regarding model can be  found in the IPYNB file
one output image is present in the results_1 folder

# Results
![Copy of 01_test_0](https://user-images.githubusercontent.com/78692554/126083351-77f2b46c-d820-4393-bcf6-2f86ab3d3b2f.png)

#Initial 
**Jaccard**: 0.6745 - **F1**: 0.8056 - **Recall**: 0.8372 - **Precision**: 0.7763 - **Acc**: 0.9641
FPS:  8.2989461854128

### Further **Morphological Closing** is done on the output which increased the **F1 score** by about **1.5 - 2%** also **Accuracy** by **2** Resulting to **98.4%** 

