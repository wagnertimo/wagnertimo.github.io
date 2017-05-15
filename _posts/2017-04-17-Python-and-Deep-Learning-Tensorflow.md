---
published: true
title: Python and Deep Learning – Tensorflow
layout: post
image:
  feature: tensorflow.svg
comments: true
categories: [Python, TensorFlow, Deep Learning]
excerpt: "General Introduction to the Deep Learning framework TensorFlow."
---

TensorFlow is a Python library for fast numerical computing created and released by Google. Like Theano, TensorFlow is intended to be used to develop deep learning models.

With the backing of Google, perhaps used in some of its production systems and used by the Google DeepMind research group, it is a platform that we cannot ignore.

Unlike Theano, TensorFlow does have more of a production focus with a capability to run on CPUs, GPUs and even very large clusters.

The goal for this post is to install TensorFlow and become familiar with the syntax of the symbolic expressions used in TensorFlow programs.

For example, you can install TensorFlow using pip. There are many different versions of TensorFlow, specialized for each platform. Select the right version for your platform on the [TensorFlow installation webpage](https://www.tensorflow.org/install).

A small example of a TensorFlow program that you can use as a starting point is listed below:

``` python
import tensorflow as tf
# declare two symbolic floating-point scalars
a = tf.placeholder(tf.float32)
b = tf.placeholder(tf.float32)
# create a simple symbolic expression using the add function
add = tf.add(a, b)
# bind 1.5 to ' a ' , 2.5 to ' b ' , and evaluate ' c '
sess = tf.Session()
binding = {a: 1.5, b: 2.5}
c = sess.run(add, feed_dict=binding)
print(c)
```

Learn more about TensorFlow on the [TensorFlow homepage](https://www.tensorflow.org).
