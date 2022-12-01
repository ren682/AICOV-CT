# AICOV-CT

Using deep learning framework to detect COVID-19 and distinguish it from community-acquired pneumonia and normal individuals using CT images.We present AICOV-CT, a two-stage deep-learning framework for detecting COVID-19. Distinguish COVID-19 from normal and community-acquired pneumonia (CAP) with the same imaging features. In the first stage, we present a hybrid method that combines white bal-ance with CLAHE for image enhancement. Then three networks are trained with high-quality CT images from different regions, and these networks are DenseNet121, ResNet50V2 and MobileNetV2. In the second stage, the trained three models are used to detect whether images contain the typical symptoms of COVID-19; the voting method is used as the final diagnosis result. It could mitigate the most severe effects of the virus by providing patients with better diagnosis and treatment.
### !!Note:The platform is for research purposes only and cannot be used for clinical use as it is not FDA approved.
## Model

![image](https://github.com/ren682/AICOV-CT/blob/main/img/Model.png)
## Dataset

Since the potential contrast in the background of the original collected image may cause deviations in the model, we used an automatic cropping algorithm to delete the background to standardize the field into a body area.The model was first trained and tested on 128,700 images that were cropped but not enhanced.The data distribution is as follows:
* [training images](https://www.kaggle.com/datasets/ironman3537/train-no-enhanced)
* [validation images](https://www.kaggle.com/datasets/ironman3537/val-no-enhanced)
* [test images](https://www.kaggle.com/datasets/ironman3537/test-no-enhanced)

DCT, White Balance and Contrast Limited Adaptive Histo-gram Equalization (CLAHE) algorithms are used to reduce the noise data of the image and add more helpful information.The model is trained and tested for the second time using the images after the data enhancement algorithm. The enhanced images can be downloaded here:
* [training images enhancement](https://www.kaggle.com/datasets/ironman3537/train-images-enhanced)
* [validate and test image enhancement](https://www.kaggle.com/datasets/ironman3537/val-test-images)

### Comparison of the effectiveness of the model for diagnosing COVID-19 before and after using image enhancement.

   ![image](https://github.com/ren682/AICOV-CT/blob/main/img/Comparison%20of%20COVID-19%20diagnosis%20using%20data%20enhancement%20algorithms.png)

## Setup

### Environment

This deep learning framework was created in the specified environment including GPU NVIDIA P100 [Nvidia, Santa Clara, Calif], 8GB, RAM 16GB.

The OS/drivers/software used to create this package were as follows:

[GPU](https://www.kaggle.com/)
CUDA version: 11.0
CUDNN version: 8005
Python version == 3.7.12

Additionally, the dependencies required to run this library are listed below:

### Dependencies

* pandas==1.3.5
* numpy==1.21.6
* matplotlib==3.5.2
* scikit_learn==1.0.2
* tensorflow==2.6.4
* cv2==4.5.4
* keras==2.6.0
* scipy==1.7.3
* torch==1.11.0
* joblib==1.0.1
## Train AICOV-CT from Scratch
To train AICOV-CT, the dataset should be structured as below:
```
-- crop
    |-- Image Enhancement
    |   `-- 224
    |       |-- Test
    |       |   |-- CAP
    |       |   |-- COVID-19
    |       |   `-- Normal
    |       |-- Train
    |       |   |-- CAP
    |       |   |-- COVID-19
    |       |   `-- Normal
    |       `-- Validation
    |           |-- CAP
    |           |-- COVID-19
    |           `-- Normal
    `-- No image enhancement
        `-- 224
            |-- Test
            |   |-- CAP
            |   |-- COVID-19
            |   `-- Normal
            |-- Train
            |   |-- CAP
            |   |-- COVID-19
            |   `-- Normal
            `-- Validation
                |-- CAP
                |-- COVID-19
                `-- Normal

```
