# traffic-sign-recognition

Python Project on Traffic Signs Recognition with 95% Accuracy using CNN & Keras


# Python Project – Traffic Signs Recognition 

You must have heard about the self-driving cars in which the passenger can fully depend on the car for traveling. But to achieve level 5 autonomous, it is necessary for vehicles to understand and follow all traffic rules.

In the world of Artificial Intelligence and advancement in technologies, many researchers and big companies like Tesla, Uber, Google, Mercedes-Benz, Toyota, Ford, Audi, etc are working on autonomous vehicles and self-driving cars. So, for achieving accuracy in this technology, the vehicles should be able to interpret traffic signs and make decisions accordingly.

# What is Traffic Signs Recognition?
There are several different types of traffic signs like speed limits, no entry, traffic signals, turn left or right, children crossing, no passing of heavy vehicles, etc. Traffic signs classification is the process of identifying which class a traffic sign belongs to.

# Traffic Signs Recognition – About the Python Project
In this Python project example, we will build a deep neural network model that can classify traffic signs present in the image into different categories. With this model, we are able to read and understand traffic signs which are a very important task for all autonomous vehicles.


# The Dataset of Python Project
For this project, we are using the public dataset available at Kaggle:

https://www.kaggle.com/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign

# Traffic Signs Dataset

The dataset contains more than 50,000 images of different traffic signs. It is further classified into 43 different classes. The dataset is quite varying, some of the classes have many images while some classes have few images. The size of the dataset is around 300 MB. The dataset has a train folder which contains images inside each class and a test folder which we will use for testing our model.

# Steps to Build the Python Project
To get started with the project, download and unzip the file


Create a Python script file and name it traffic_signs.py in the project folder.

Our approach to building this traffic sign classification model is discussed in four steps:

1 Explore the dataset
2 Build a CNN model
3 Train and validate the model
4 Test the model with test dataset

# Step 1: Explore the dataset

Our ‘train’ folder contains 43 folders each representing a different class. The range of the folder is from 0 to 42. With the help of the OS module, we iterate over all the classes and append images and their respective labels in the data and labels list.





# Step 2: Build a CNN model

To classify the images into their respective categories, we will build a CNN model (Convolutional Neural Network).
CNN is best for image classification purposes.

The architecture of our model is:

2 Conv2D layer (filter=32, kernel_size=(5,5), activation=”relu”)
MaxPool2D layer ( pool_size=(2,2))
Dropout layer (rate=0.25)
2 Conv2D layer (filter=64, kernel_size=(3,3), activation=”relu”)
MaxPool2D layer ( pool_size=(2,2))
Dropout layer (rate=0.25)
Flatten layer to squeeze the layers into 1 dimension
Dense Fully connected layer (256 nodes, activation=”relu”)
Dropout layer (rate=0.5)
Dense layer (43 nodes, activation=”softmax”)



# Steps 3: Train and validate the model

After building the model architecture, we then train the model using model.fit(). I tried with batch size 32 and 64. Our model performed better with 64 batch size. And after 15 epochs the accuracy was stable.

![image](https://user-images.githubusercontent.com/61861869/123510460-53d8f580-d699-11eb-8c73-8c609902f63e.png)



Our model got a 95% accuracy on the training dataset. With matplotlib, we plot the graph for accuracy and the loss.


![image](https://user-images.githubusercontent.com/61861869/123510452-373cbd80-d699-11eb-8f07-b1f17b10be59.png)



# Step 4: Test our model with test dataset

Our dataset contains a test folder and in a test.csv file, we have the details related to the image path and their respective class labels. We extract the image path and labels using pandas. Then to predict the model, we have to resize our images to 30×30 pixels and make a numpy array containing all image data. From the sklearn.metrics, we imported the accuracy_score and observed how our model predicted the actual labels. We achieved a 95% accuracy in this model.





![image](https://user-images.githubusercontent.com/61861869/123510651-5be56500-d69a-11eb-8906-e7692850934c.png)



# Summary
In this Python project with source code, we have successfully classified the traffic signs classifier with 95% accuracy and also visualized how our accuracy and loss changes with time, which is pretty good from a simple CNN model.
