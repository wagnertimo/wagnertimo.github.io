---
published: true
title: Python and Deep Learning – Theano
layout: post
comments: true
---

Theano is a Python library for fast numerical computation to aid in the development of deep learning models.

At its heart, Theano is a compiler for mathematical expressions in Python. It knows how to take your structures and turn them into very efficient code that uses NumPy and efficient native libraries to run as fast as possible on CPUs or GPUs.

The actual syntax of Theano expressions is symbolic, which can be off-putting to beginners used to normal software development. Specifically, expression are defined in the abstract sense, compiled and later actually used to make calculations.

In this lesson, your goal is to install Theano and write a small example that demonstrates the symbolic nature of Theano programs.

For example, you can install Theano using pip as follows:

```sh
sudo pip install Theano
```

A small example of a Theano program that you can use as a starting point is listed below:
``` python
import theano
from theano import tensor
# declare two symbolic floating-point scalars
a = tensor.dscalar()
b = tensor.dscalar()
# create a simple expression
c = a + b
# convert the expression into a callable object that takes (a,b)
# values as input and computes a value for c
f = theano.function([a,b], c)
# bind 1.5 to 'a', 2.5 to 'b', and evaluate 'c'
result = f(1.5, 2.5)
print(result)
```

Learn more about Theano on the [Theano homepage](http://deeplearning.net/software/theano/?__s=rvasa3puiemv9zazwcff).
