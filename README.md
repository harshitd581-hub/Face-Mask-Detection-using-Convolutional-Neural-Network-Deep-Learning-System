Face Mask Detection using CNN (Deep Learning)

1. Project Overview
This project is based on Deep Learning using Convolutional Neural Networks (CNN).
The main objective of this system is to detect whether a person is wearing a face mask or not using images.
During the COVID-19 pandemic, wearing masks became an important safety measure. This system can automatically detect mask usage from images and can be used in public places such as airports, hospitals, offices, and transportation systems.
The model is trained on two categories of images:
With Mask
Without Mask
After training, the model can predict whether a new image contains a person wearing a mask or not.
## Dataset Source
The dataset used in this project was not manually downloaded and uploaded. Instead, it was directly imported from Kaggle using the Kaggle API.
Using the Kaggle API allows the dataset to be automatically downloaded into the project environment, making the data collection process faster and more efficient. This method ensures that the dataset is fetched directly from the original source.
The dataset contains two categories of images:
With Mask
Without Mask
These images are used to train and evaluate the deep learning model for face mask detection.
The dataset can also be downloaded manually from the following link:
https://www.kaggle.com/datasets/omkargurav/face-mask-dataset
## BUT IF YOU WANT YOU CAN DOWNLOAD DATA DIRECT FROM KAGGLE.

3. Dataset Collection
The dataset used in this project is downloaded from Kaggle.
It contains images of people wearing masks and people without masks.
The dataset is divided into two folders:
With Mask – images of people wearing face masks
Without Mask – images of people not wearing face masks
Total images in the dataset:
With mask images ≈ 3725
Without mask images ≈ 3828
Total dataset size ≈ 7553 images
These images are used to train and test the deep learning model.

5. Importing Required Libraries
Several Python libraries are used in this project to perform different tasks such as image processing, numerical computation, and deep learning.
For example:
Numerical operations
Image reading and processing
Data visualization
Deep learning model creation
Dataset splitting
These libraries help in building and training the CNN model efficiently.

7. Loading the Dataset
After downloading the dataset, the program reads all image files from the two folders:
the with_mask folder
the without_mask folder
Each folder contains hundreds of images. The system scans these folders and creates a list of all image file names so that they can be processed later.
This step helps the program understand how many images are available in each category.

9. Creating Labels
Machine learning models require labels to understand which image belongs to which category.
Therefore, labels are assigned as follows:
With Mask → Label = 1
Without Mask → Label = 0
This means:
If an image contains a mask, it will be marked as 1
If an image does not contain a mask, it will be marked as 0
These labels help the model learn the difference between masked and unmasked faces.

11. Image Processing
Before feeding images into the neural network, several preprocessing steps are applied.
Image Resizing
All images are resized to 128 × 128 pixels.
Reason: Neural networks require all input images to have the same dimensions.
RGB Conversion
All images are converted into RGB format.
RGB format contains three channels:
Red
Green
Blue
This ensures that every image has consistent color information.
Conversion to Numerical Data
Images cannot be directly processed by neural networks.
Therefore, each image is converted into numerical arrays.
Each pixel of the image is represented by numbers indicating color intensity.
For example:
0 = black
255 = white
After conversion, the image becomes a matrix of numbers.

13. Creating Image Dataset
After preprocessing, all processed images are stored together in a data structure.
Each image now has a shape like:
Height × Width × Color Channels
For example:
128 × 128 × 3
Where:
128 = height
128 = width
3 = RGB channels
The dataset now contains 7553 images in numerical form.

15. Train-Test Split
To evaluate the model properly, the dataset is divided into two parts:
Training Data
Used to train the neural network so it can learn patterns from the images.
Testing Data
Used to check how well the trained model performs on unseen images.
Usually the dataset is split approximately into:
80% training data
20% testing data
This helps ensure that the model generalizes well to new images.

17. Data Normalization
Pixel values in images range from 0 to 255.
To improve model performance, these values are scaled between 0 and 1.
This process is called normalization.
Benefits of normalization:
Faster training
Better accuracy
More stable learning

19. Building the CNN Model
The model used in this project is a Convolutional Neural Network (CNN).
CNNs are widely used for image classification tasks.
The model contains several layers.
Convolution Layer
This layer extracts important features from images such as:
edges
shapes
textures
mask patterns
These features help the model understand the content of the image.
Max Pooling Layer
This layer reduces the size of the feature maps.
Benefits:
reduces computation
focuses on important features
prevents overfitting
Flatten Layer
The flatten layer converts 2-dimensional feature maps into a one-dimensional vector so that it can be used by fully connected layers.
Dense Layer
Dense layers learn complex relationships between extracted features.
These layers help the model decide whether the face contains a mask or not.
Dropout Layer
Dropout helps prevent overfitting.
Overfitting occurs when the model memorizes training data instead of learning general patterns.
Dropout randomly disables some neurons during training to improve generalization.
Output Layer
The output layer predicts the final class.
There are two possible outputs:
Mask
No Mask
The model assigns probabilities to both classes and selects the most likely one.

21. Model Training
During training, the model learns patterns from the training dataset.
The training process runs for several epochs.
An epoch means the model processes the entire training dataset once.
During training, the model calculates:
Loss (prediction error)
Accuracy (correct predictions)
As training progresses:
Loss decreases
Accuracy increases
This indicates that the model is learning successfully.

23. Model Evaluation
After training, the model is tested on the testing dataset.
The evaluation step calculates the model's final performance.
In this project, the model achieves approximately:
Test Accuracy ≈ 92%
This means the model correctly classifies about 92 out of 100 images.

25. Loss and Accuracy Graphs
Two graphs are used to analyze model performance.
Loss Graph
Shows:
Training Loss
Validation Loss
Lower loss means the model is making fewer errors.
Accuracy Graph
Shows:
Training Accuracy
Validation Accuracy
Increasing accuracy means the model is learning correctly.

27. Predictive System
After training, the system can predict new images.
Steps performed by the system:
The user provides the path of a new image.
The image is read and displayed.
The image is resized to the required size.
Pixel values are normalized.
The image is passed to the trained CNN model.
The model predicts the category.

29. Final Prediction
Based on the prediction result, the system displays:
"The person in the image is wearing a mask"
or
"The person in the image is not wearing a mask"
This allows automatic detection of mask usage from images.
30. Applications
This system can be used in many real-world applications:
Airports
Railway stations
Hospitals
Offices
Shopping malls
Public transport
Security monitoring systems

32. Conclusion
This project demonstrates how Convolutional Neural Networks can be used for image classification tasks such as face mask detection.
The trained model achieved an accuracy of approximately 92%, showing that deep learning can effectively identify whether a person is wearing a mask or not.
This type of system can help automate public safety monitoring and reduce manual supervision.
