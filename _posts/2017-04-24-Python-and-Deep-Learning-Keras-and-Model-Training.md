---
published: false
title: Python and Deep Learning – Keras and Model Training
layout: post
---
One can learn a lot about neural networks and deep learning models by observing their performance over time during training.

Keras provides the capability to register callbacks when training a deep learning model.

One of the default callbacks that is registered when training all deep learning models is the History callback. It records training metrics for each epoch. This includes the loss and the accuracy (for classification problems) as well as the loss and accuracy for the validation dataset if one is set.

The history object is returned from calls to the fit() function used to train the model. Metrics are stored in a dictionary in the history member of the object returned.

Your goal for this lesson is to investigate the history object and create plots of model performance during training.

For example, you can print the list of metrics collected by your history object as follows:

```r
# list all data in history
history = model.fit(...)
print(history.history.keys())
```

You can learn more about the History object and the [callback API in Keras](https://keras.io/callbacks/?__s=rvasa3puiemv9zazwcff).
