---
published: false
title: Python and Deep Learning – Keras and Regularization
layout: post
---
A big problem with neural networks is that they can overlearn your training dataset. This is called **overfitting**.

Dropout is a simple yet very effective technique for reducing dropout and has proven useful in large deep learning models.

Dropout is a technique where randomly selected neurons are ignored during training. They are dropped-out randomly. This means that their contribution to the activation of downstream neurons is temporally removed on the forward pass and any weight updates are not applied to the neuron on the backward pass.

You can add a dropout layer to your deep learning model using the Dropout layer class.

In this lesson, your goal is to experiment with adding dropout at different points in your neural network and set to different probability values.

For example, you can create a dropout layer with the probability of 20% and add it to your model as follows:

```r
from keras.layers import Dropout
...
model.add(Dropout(0.2))
```

You can learn more about [dropout in Keras](https://keras.io/layers/core/?__s=rvasa3puiemv9zazwcff).
