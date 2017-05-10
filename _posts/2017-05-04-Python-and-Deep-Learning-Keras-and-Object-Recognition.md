---
published: false
title: Python and Deep Learning – Keras and Object Recognition
layout: post
---
Object recognition is a problem where your model must indicate what is in a photograph.

Deep learning models achieve state of the art results in this problem using deep convolutional neural networks.

A popular standard dataset for evaluating models on this type of problem is called CIFAR-10. It contains 60,000 small photographs, each of one of 10 objects, like a cat, ship or airplane.

As with the MNIST dataset, Keras provides a convenient function that you can use to load the dataset, and it will download it to your computer the first time you try to load it. The dataset is a 163 MB so it may take a few minutes to download.

Your goal in this lesson is to develop a deep convolutional neural network for the CIFAR-10 dataset. I would recommend a repeated pattern of convolution and pooling layers. Consider experimenting with drop-out and long training times.

For example, you can load the CIFAR-10 dataset in Keras and prepare it for use with a convolutional neural network as follows:

```r
from keras.datasets import cifar10
from keras.utils import np_utils
# load data
(X_train, y_train), (X_test, y_test) = cifar10.load_data()
# normalize inputs from 0-255 to 0.0-1.0
X_train = X_train.astype('float32') X_test = X_test.astype('float32')
X_train = X_train / 255.0
X_test = X_test / 255.0
# one hot encode outputs
y_train = np_utils.to_categorical(y_train)
y_test = np_utils.to_categorical(y_test)
```
