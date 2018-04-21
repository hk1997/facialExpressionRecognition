Data Source:
https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data

Data Description: The data consists of 48x48 pixel grayscale images of faces. The faces have been automatically registered so that the face is more or less centered and occupies about the same amount of space in each image. The task is to categorize each face based on the emotion shown in the facial expression in to one of seven categories (0=Angry, 1=Disgust, 2=Fear, 3=Happy, 4=Sad, 5=Surprise, 6=Neutral).

The model has been trained on GoogleColab.

facial_recognition.ipynb contains code for model and data_to_numpy_arrays.ipynb helps in preparation of data from csv to .npy arrays.

Model Architecture: We are using a multilayered convolutional neural network based on architecture of AlexNet.

Model Summary:
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d_21 (Conv2D)           (None, 48, 48, 96)        960       
_________________________________________________________________
max_pooling2d_11 (MaxPooling (None, 24, 24, 96)        0         
_________________________________________________________________
conv2d_22 (Conv2D)           (None, 23, 23, 256)       98560     
_________________________________________________________________
conv2d_23 (Conv2D)           (None, 22, 22, 384)       393600    
_________________________________________________________________
conv2d_24 (Conv2D)           (None, 21, 21, 384)       590208    
_________________________________________________________________
max_pooling2d_12 (MaxPooling (None, 10, 10, 384)       0         
_________________________________________________________________
flatten_6 (Flatten)          (None, 38400)             0         
_________________________________________________________________
activation_21 (Activation)   (None, 38400)             0         
_________________________________________________________________
dense_16 (Dense)             (None, 1024)              39322624  
_________________________________________________________________
activation_22 (Activation)   (None, 1024)              0         
_________________________________________________________________
dropout_11 (Dropout)         (None, 1024)              0         
_________________________________________________________________
dense_17 (Dense)             (None, 1024)              1049600   
_________________________________________________________________
activation_23 (Activation)   (None, 1024)              0         
_________________________________________________________________
dropout_12 (Dropout)         (None, 1024)              0         
_________________________________________________________________
dense_18 (Dense)             (None, 7)                 7175      
_________________________________________________________________
activation_24 (Activation)   (None, 7)                 0         
=================================================================
Total params: 41,462,727
Trainable params: 41,462,727
Non-trainable params: 0
_________________________________________________________________

Results:  We have achieved an accuracy of 88.6% on test set that is appended in the csv. This accuracy is better than those of people in the public leaderboard of kaggle contests.
