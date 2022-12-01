# AICOV-CT
Using deep learning framework to detect COVID-19 and distinguish it from community-acquired pneumonia and normal individuals using CT images
## MODEL
![image](https://github.com/ren682/AICOV-CT/blob/main/img/Model.png)
## DATA
Since the potential contrast in the background of the original collected image may cause deviations in the model, we used an automatic cropping algorithm to delete the background to standardize the field into a body area，no data enhancement algorithm is used at this point.![train data](https://www.kaggle.com/datasets/ironman3537/train-no-enhanced);![val data](https://www.kaggle.com/datasets/ironman3537/val-no-enhanced);![test data](https://www.kaggle.com/datasets/ironman3537/test-no-enhanced)
