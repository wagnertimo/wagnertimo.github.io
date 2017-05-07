---
published: false
title: Python and Deep Learning – Keras and Classifiers
layout: post
---

The scikit-learn library is a general purpose machine learning framework in Python built on top of SciPy.

Scikit-learn excels at tasks such as evaluating model performance and optimizing model hyperparameters in just a few lines of code.

Keras provides a wrapper class that allows you to use your deep learning models with scikit-learn. For example, an instance of KerasClassifier class in Keras can wrap your deep learning model and be used as an Estimator in scikit-learn.

When using the KerasClassifier class, you must specify the name of a function that the class can use to define and compile your model. You can also pass additional parameters to the constructor of the KerasClassifier class that will be passed to the model.fit() call later, like the number of epochs and batch size.

In this lesson, your goal is to develop a deep learning model and evaluate it using k-fold cross validation.

For example, you can define an instance of the KerasClassifier and the custom function to create your model as follows:

```r
# Function to create model, required for KerasClassifier
def create_model():
    # Create model
    model = Sequential()
    ...
    # Compile model
    model.compile(...)
    return model

# create classifier for use in scikit-learn
model = KerasClassifier(build_fn=create_model, epochs=150, batch_size=10)
# evaluate model using 10-fold cross validation in scikit-learn
kfold = StratifiedKFold(n_splits=10, shuffle=True, random_state=seed)
results = cross_val_score(model, X, Y, cv=kfold)
```

Learn more about using your Keras deep learning models with scikit-learn on the [Wrappers for the Sciki-Learn API webpage](https://keras.io/scikit-learn-api/?__s=rvasa3puiemv9zazwcff).
