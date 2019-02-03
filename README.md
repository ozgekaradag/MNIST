# MNIST

### MNIST handwritten Images:
It is a data-set, consisting images of handwritten digits from 0 to 9. Each image is a monochrome , 28 * 28 pixel. See the example below:

<img src="https://www.tensorflow.org/images/mnist_0-9.png" width="300">




### Objective:
Train a computer system to first understand what are handwritten images of digits an then test the system to predict new handwritten images correctly. We will feed our system with MNIST dataset and test it with random images to check the accuracy of its predictions.

### Pre-requisite:
* Basic knowledge of python scripting, Python 3.6.
* An idea of what is Machine learning and TensorFlow.
* Vigor to learn something new.

### Placeholders:
Placeholders are different from variables. They are parameters which are created to hold the training data, in this case it would be training images. MNIST images are in the shape of (28*28). These would be flattened into (None *784) shape tensor. ‘None’ indicates that it could be of any size.

### Weights and Biases:
The initial values are set to zeros for Weight and Bias because it is going to be changed when the computation happens. Thus, it does not matter what are the initial values. ‘w’ is of (784 * 10) shape because 784 features and 10 outputs are present. ‘b’ is of the shape 10 because there are 10 outputs from 0 till 9 (digits).

### Prediction Model:
x and w are matrices which are multiplied and added to a bias. The softmax function takes values and makes the total to be 1. This way it can be used as probability values making it uniform to judge which digit (0 -9) has higher chances of being predicted.

### Cross-Entropy function:
The cross-entropy function is a cost or loss function. It compares the true values to the predicted values. The goal is to minimize the loss.

### Gradient Descent Optimizer:
When a model graph is formed using the cross-entropy function, we would want to find a point where the loss is at the minimum. This is done using the Gradient Descent optimizer. It moves towards the part of the graph where the value of the graph is lesser. The steps or the learning rate can be set manually. If a very small learning rate like 0.001 is set it would take forever for the system to reach to the point where loss is minimum but it would be more accurate. If the learning is rate is set high then the system might produce quick but false results a false results.

### Multi-Convolutional Layer:
Here, we are using more layers, weights and biases to refine our model and increase accuracy.
Our first convolutional layer has 32 features for each 5*5 patch. Its weight tensor will be of a shape of [5,5,1,32]. First two dimensions are the patch size, the next is the input channel and the last number is the output channel.

To apply the convolutional layer, x is reshaped to 4D tensor. 28*28 is the image width and height and the final dimension is the number of color channels.

Then ReLU function is applied to bring the negative values to 0 and keep the positive values as it is. Maxpool reduces the image size to 14*14.

The second convolutional layer has 64 features for each 5*5 patch.

Now that the image size has been reduces to 7*7 we add a fully-connected layer with 1024 neurons.

### Prediction Accuracy:
0.9919
