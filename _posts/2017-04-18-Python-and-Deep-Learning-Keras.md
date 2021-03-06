---
published: true
title: Python and Deep Learning – Keras
layout: post
image:
  feature: keras.svg
comments: true
categories: [Python, Keras, Deep Learning]
excerpt: "General Introduction to the Deep Learning API Keras."
---

The difficulty of [Theano](../2017-04/Python-and-Deep-Learning-Theano) and [TensorFlow](../2017-04/Python-and-Deep-Learning-Tensorflow) is that it can take a lot of code to create even very simple neural network models.

These libraries were designed primarily as a platform for research and development more than for the practical concerns of applied deep learning.

The Keras library addresses these concerns by providing a wrapper for both Theano and TensorFlow. It provides a clean and simple API that allows you to define and evaluate deep learning models in just a few lines of code.

Because of the ease of use and because it leverages the power of Theano and TensorFlow, Keras is quickly becoming the go-to library for applied deep learning.

The focus of Keras is the concept of a model. The life-cycle of a model can be summarized as follows:

1. *Define your model* - Create a Sequential model and add configured layers.
2. *Compile your model* - Specify loss function and optimizers and call the `compile()` function on the model.
3. *Fit your model* - Train the model on a sample of data by calling the `fit()` function on the model.
4. *Make predictions* - Use the model to generate predictions on new data by calling functions such as `evaluate()` or `predict()` on the model.
Your goal for this lesson is to install Keras.

For example, you can install Keras using pip:
But for a proper use please make sure you already installed [Theano](../2017-04/Python-and-Deep-Learning-Theano) or [TensorFlow](../2017-04/Python-and-Deep-Learning-Tensorflow). By default Keras uses Tensorflow as its tensor manipulation library
```sh
sudo pip install keras
```

You can learn more about the Keras library on the [Keras homepage](https://keras.io).

Or check out this [post](../2017-04-19-Python-and-Deep-Learning-Keras-and-Building-an-ANN) to apply the 4 step life-cycle of a model on an example dataset.
