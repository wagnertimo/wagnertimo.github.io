---
published: false
title: Python and Deep Learning – Keras and ModelCheckpoint
layout: post
---
Application checkpointing is a fault tolerance technique for long running processes.

The Keras library provides a checkpointing capability by a callback API. The ModelCheckpoint callback class allows you to define where to checkpoint the model weights, how the file should be named and under what circumstances to make a checkpoint of the model.

Checkpointing can be useful to keep track of the model weights in case your training run is stopped prematurely. It is also useful to keep track of the best model observed during training.

In this blog post the goal is to use the ModelCheckpoint callback in Keras to keep track of the best model observed during training.

You could define a ModelCheckpoint that saves network weights to the same file each time an improvement is observed. For example:

```r
from keras.callbacks import ModelCheckpoint
...
checkpoint = ModelCheckpoint('weights.best.hdf5', monitor='val_acc', save_best_only=True, mode='max')
callbacks_list = [checkpoint]
# Fit the model
model.fit(..., callbacks=callbacks_list)
```

Learn more about using the [ModelCheckpoint callback in Keras](https://keras.io/callbacks/).
