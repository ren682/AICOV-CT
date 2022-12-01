# AICOV-CT
Using deep learning framework to detect COVID-19 and distinguish it from community-acquired pneumonia and normal individuals using CT images.We present AICOV-CT, a two-stage deep-learning framework for detecting COVID-19. Distinguish COVID-19 from normal and community-acquired pneumonia (CAP) with the same imaging features. In the first stage, we present a hybrid method that combines white bal-ance with CLAHE for image enhancement. Then three networks are trained with high-quality CT images from different regions, and these networks are DenseNet121, ResNet50V2 and MobileNetV2. In the second stage, the trained three models are used to detect whether images contain the typical symptoms of COVID-19; the voting method is used as the final diagnosis result. It could mitigate the most severe effects of the virus by providing patients with better diagnosis and treatment.
### !!Note:The platform is for research purposes only and cannot be used for clinical use as it is not FDA approved.
## Model
![image](https://github.com/ren682/AICOV-CT/blob/main/img/Model.png)
## Dataset
Since the potential contrast in the background of the original collected image may cause deviations in the model, we used an automatic cropping algorithm to delete the background to standardize the field into a body area.The model was first trained and tested on 128,700 images that were cropped but not enhanced.The data distribution is as follows:
* [train data](https://www.kaggle.com/datasets/ironman3537/train-no-enhanced);
* [val data](https://www.kaggle.com/datasets/ironman3537/val-no-enhanced);
* [test data](https://www.kaggle.com/datasets/ironman3537/test-no-enhanced)
