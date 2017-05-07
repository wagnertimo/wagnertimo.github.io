---
published: false
title: Python and Deep Learning – Keras and Convolutional Neural Networks
layout: post
---
This blog post focuses on Convolutional Neural Networks. First, the basics and terminology are explained. And then I will give you two examples for using this powerful artificial neural network technique.

## Introduction

Convolutional Neural Networks (CNNs) expect and preserve the spatial relationship between pixels in images by learning internal feature representations using small squares of input data.

Feature are learned and used across the whole image, allowing for the objects in your images to be shifted or translated in the scene and still detectable by the network. It is this reason why this type of network is so useful for object recognition in photographs, picking out digits, faces, objects and so on with varying orientation.

There are three types of layers in a Convolutional Neural Network:
Convolutional Layers comprised of filters and feature maps.
Pooling Layers that down sample the activations from feature maps.
Fully-Connected Layers that plug on the end of the model and can be used to make predictions.
In this lesson, you are to familiarize yourself with the terminology used when describing convolutional neural networks.

This may require a little research on your behalf.

Don’t worry too much about how they work just yet, just learn the terminology and configuration of the various layers used in this type of network.

## Example 1: The MNIST dataset - Digit recognition

The MNIST dataset is a standard problem for evaluating algorithms on the problem of handwriting digit recognition. It contains 60,000 images of digits that can be used to train a model and 10,000 images that can be used to evaluate its performance.

State of the art results can be achieved on the MNIST problem using convolutional neural networks. Keras makes loading the MNIST dataset dead easy.

In this lesson, your goal is to develop a very simple convolutional neural network for the MNIST problem comprised of one convolutional layer, one max pooling layer and one dense layer to make predictions.

For example, you can load the MNIST dataset in Keras as follows:

```r
from keras.datasets import mnist
...
(X_train, y_train), (X_test, y_test) = mnist.load_data()
It may take a moment to download the files to your computer.
```

As a tip, the Keras `Convolutional2D` layer that you will use as your first hidden layer expects image data in the format channels x width x height, where the MNIST data has 1 channel because the images are grayscale and a width and height of 28 pixels. You can easily reshape the MNIST dataset as follows:

```r
X_train = X_train.reshape(X_train.shape[0], 1, 28, 28)
X_test = X_test.reshape(X_test.shape[0], 1, 28, 28)
```

You will also need to one hot encode the output class value, that Keras also provides a handy helper function to achieve:

```r
from keras.utils import np_utils
...
y_train = np_utils.to_categorical(y_train)
y_test = np_utils.to_categorical(y_test)
```

As a final tip here is a model definition that you can use as a starting point:

```r
model = Sequential()
model.add(Conv2D(32, (3, 3), padding='valid', input_shape=(1, 28, 28),
activation='relu'))
model.add(MaxPooling2D(pool_size=(2, 2)))
model.add(Flatten())
model.add(Dense(128, activation='relu'))
model.add(Dense(num_classes, activation='softmax'))
model.compile(loss='categorical_crossentropy', optimizer='adam', metrics=['accuracy'])
```
