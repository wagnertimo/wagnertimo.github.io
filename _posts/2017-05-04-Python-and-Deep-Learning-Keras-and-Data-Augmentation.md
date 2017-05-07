---
published: false
title: Python and Deep Learning – Keras and Data Augmentation
layout: post
---
Data preparation is required when working with neural network and deep learning models.

Increasingly data augmentation is also required on more complex object recognition tasks. This is where images in your dataset are modified with random flips and shifts. This in essence makes your training dataset larger and helps your model to generalize the position and orientation of objects in images.

Keras provides an image augmentation API that will create modified versions of images in your dataset just-in-time. The ImageDataGenerator class can be used to define the image augmentation operations to perform which can be fit to a dataset and then used in place of your dataset when training your model.

Your goal with this lesson is to experiment with the Keras image augmentation API using a dataset you are already familiar with from a previous lesson like MNIST or CIFAR-10.

For example, the example below creates random rotations of up to 90 degrees of images in the MNIST dataset.

```r
# Random Rotations
from keras.datasets import mnist
from keras.preprocessing.image import ImageDataGenerator
from matplotlib import pyplot
# load data
(X_train, y_train), (X_test, y_test) = mnist.load_data()
# reshape to be [samples][pixels][width][height]
X_train = X_train.reshape(X_train.shape[0], 1, 28, 28)
X_test = X_test.reshape(X_test.shape[0], 1, 28, 28)
# convert from int to float
X_train = X_train.astype('float32')
X_test = X_test.astype('float32')
# define data preparation
datagen = ImageDataGenerator(rotation_range=90)
# fit parameters from data
datagen.fit(X_train)
# configure batch size and retrieve one batch of images
for X_batch, y_batch in datagen.flow(X_train, y_train, batch_size=9):
    # create a grid of 3x3 images
    for i in range(0, 9):
        pyplot.subplot(330 + 1 + i)
        pyplot.imshow(X_batch[i].reshape(28, 28), cmap=pyplot.get_cmap('gray'))
    # show the plot
    pyplot.show()
    break
```
   
You can learn more about the [Keras image augmentation API](https://keras.io/preprocessing/image/?__s=rvasa3puiemv9zazwcff).
