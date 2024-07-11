**__A Traffic Sign Classifier for Autonomous Vehicles__** 

This project is a deep learning model built upon convolutional neural networks (CNNs) and fully connected layers to classify traffic signs in an autonomous vehicle. 

**Dataset**

The German Traffic Sign Recognition Benchmark (GTSRB) is a multi-class, single-image classification challenge held at the International Joint Conference on Neural Networks (IJCNN) 2011. The dataset contains metadata file, train.csv and test.csv files, a train folder, and a test folder that contains images and their corresponding classifications.

For this project, only a 10% portion of the train folder was used for both training and testing the classifier. When loaded to the Colab runtime, each image was resized to a (128, 128) array, converted to a tensor, and normalized. The trainset and testset were then created by randomly sampling 80% and 20% of the miniature train folder, both finally loaded as tensor datasets using the DataLoader module.  


**Building The Classifier**

- 3 convolutional layers that take 3 128x128 images as the input and outputs 64 downsized images of size 16x16 (After each convolutional layer, pooling with kernel size equal to 2x2 occurs)
- A dropout function that drops 25% of the dataset to avoid overfitting
- 2 fully connected layers that flatten the downsized images and learn to generate classifications.
  - The first fully connected layer has an input size of 128x(16x16) (128 images of size 16x16) and the ReLU activation function
  - The second layer has an output size of 43 - representing the probability of each class among the 43 classes.

**Hyperparameters Setting**
