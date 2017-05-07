---
published: false
title: Python and Deep Learning – Keras and Lifting Performance
layout: post
---
You can often get a boost in the performance of your model by using a learning rate schedule.

Often called an adaptive learning rate or an annealed learning rate, this is a technique where the learning rate used by stochastic gradient descent changes while training your model.

Keras has a time-based learning rate schedule built into the implementation of the stochastic gradient descent algorithm in the SGD class.

When constructing the class, you can specify the decay which is the amount that your learning rate (also specified) will decrease each epoch. When using learning rate decay you should bump up your initial learning rate and consider adding a large momentum value such as 0.8 or 0.9.

Your goal in this lesson is to experiment with the time-based learning rate schedule built into Keras.

For example, you can specify a learning rate schedule that starts at 0.1 and drops by 0.0001 each epoch as follows:

```r
from keras.optimizers import SGD
...
sgd = SGD(lr=0.1, momentum=0.9, decay=0.0001, nesterov=False)
model.compile(..., optimizer=sgd)
```

You can learn more about the [SGD class in Keras](https://keras.io/optimizers/?__s=rvasa3puiemv9zazwcff).
