# Binary Classifier for Grasp success detection using Pretrained “Resnet model” and “model trained with CIFAR 10 dataset”


## 1.	MODEL DESCRIPTION:
Two different models were trained to check which one performs better. 
a)Pre-trained Resnet34 Model:
-The Pre trained model was taken and it was modified so that it could take our dataset. The last layer was changed to classify into two labels success and not success.
-Starting CNN layers (1st to 25th) were freezed and model was let to train only with partial layers active.

b)Model trained with CIFAR 10 dataset:
-Following model architecture was taken and let to train with Cifar 10 dataset for 10 epochs. Once it was trained, again the modifications were done so that it could take our dataset and classify into two labels.
 
-First two CNN layers were freezed and model was let to train only with linear layers as active.


## 2.	Data Description
Images for each class (Successful and Unsuccessful Grasp) were extracted from videos of an Allegro robotic hand trying to grasp an object. These were used to retrain both the models after freezing classifier layers in models.

https://user-images.githubusercontent.com/70087843/114982614-e87ad800-9e4c-11eb-9d35-ef937b81bbcb.png

https://user-images.githubusercontent.com/70087843/114982708-07796a00-9e4d-11eb-95c8-ac393174785b.png



The sample size for both class was increased to 1000 using transformation.
 


## 3.	Training reports
• 2000 images were used to train the model (1000 from each class).
• After each epoch class accuracy was obtained using the same images again (2000).
• Test accuracy was obtained at the end using 32 (Not Successful: 16 and Successful: 16) new images which were not used in the training and validation.
• Both models were trained for 4 epochs and following results were obtained:

![image](https://user-images.githubusercontent.com/70087843/116761741-ac5f7f80-a9d5-11eb-869c-753189ec5d45.png)


 



## 4.	Conclusion
The method of using pre-trained model to train it again with new data is called transferred learning. Initial layers of the neural network are responsible for extracting features from the images. The last layers are responsible for classifying high level features extracted. Already trained model can be modified to freeze initial layers. This modified can then be trained with our own dataset. 

One of the major limitations of training our own created model is that we may need large number of dataset to extract features, to overcome this limitation, we can use the already established large dataset like CIFAR10 to extract features and then again freeze the features layer and train it with our own small dataset.

Pretrained Resnet 34 model which was trained with our own dataset after freezing CNN layers was found to be getting more accurate over epochs.


### Files: 
DATASET: 
Extracted Images (Successful): https://drive.google.com/drive/folders/1oUyCLogBPbyN6Ju7gkbbHfY4AuJ12HSo?usp=sharing

Extracted Images (Unsuccessful): https://drive.google.com/drive/folders/1HwL92VNdifV6ecPpF3O3ChKgq_rMCULj?usp=sharing


IMAGE SAMPLES FOR TEST: https://drive.google.com/drive/folders/1blB7_SYCXL0S5JXrheKZ_y7Xmv7ukxfx?usp=sharing






