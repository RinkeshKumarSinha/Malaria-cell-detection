
## Summary
Malaria is a serious and potentially life-threatening disease caused by parasites that are transmitted to people through the bites of infected mosquitoes. It is a major public health problem, and can lead to severe illness and death if left untreated. Early diagnosis is essential as it can help save the severity or deteriorating health condition. One approach that we can use in the diagnosis of malaria is the use of convolutional neural networks (CNNs), which are a type of artificial intelligence model that is particularly well-suited for image classification tasks. CNNs can be trained to recognize patterns in images of infected blood cells and make a diagnosis based on those patterns.

The dataset that we are having contains about 27560 images consisting 13780 parasitized images and 13780 healthy cell images. 
![App Screenshot](https://raw.githubusercontent.com/RinkeshKumarSinha/Malaria-cell-detection/main/kaggle/input/malarial-cell-image/Malarial%20Cell%20Image%20Data%20/cell_images/Parasitized/C100P61ThinF_IMG_20150918_144104_cell_162.png)

Parasitized Image                         

 

![App Screenshot](https://raw.githubusercontent.com/RinkeshKumarSinha/Malaria-cell-detection/main/kaggle/input/malarial-cell-image/Malarial%20Cell%20Image%20Data%20/cell_images/Uninfected/C100P61ThinF_IMG_20150918_144104_cell_131.png)
 Healthy Image

As we can also differentiate quite easily that the parasitized image contains red spots, now we have to train such a model that can identify these spots. 

Now the backend environment that we’re going to use is TensorFlow. 

Let’s get started with the project.

We’re going to divide the project into 3 parts. 

Pre-Processing the Data 
Creating a CNN model
Accuracy and Saving model
 
Pre-Processing the Data: 

Pre-processing image data before creating a CNN model is an important step in the machine learning process. It involves cleaning and normalizing the data, extracting relevant features, Pre-processing helps to improve the quality and consistency of the data, which can lead to a more accurate and effective model. In Pre-Processing we convert the image data into NumPy arrays so that the model can understand it and extract the features. Also, as the images vary in size we will resize them to a common size. After preprocessing and resizing we will split the data into test and train datasets and also change the labels into categorical labels so that the model won’t consider the labels as some sought of preference. 

CNN Architecture: 
![App Screenshot](https://miro.medium.com/v2/resize:fit:1400/1*CnNorCR4Zdq7pVchdsRGyw.png)
Our Model will consist of an input Layer. 3 Convolutional Layers, 3 Pooling Layers, 3 Normalization Layers and 3 Dropout Layers. Then the output of the final layer will be sent to a Flatten Layer where we will pass it to 2 dense layers, normalize it again and use dropout and then finally use a dense layer to find the output . This model will be then compiled and saved and used for deployment. All these layers will have the relevant activation function, padding and the kernel size.
