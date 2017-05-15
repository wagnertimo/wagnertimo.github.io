---
published: false
comments: true
layout: post
title: Machine Learning 101 - The Basics
---
Here you should get an overview about the most common terms and techniques in Machine Learning.


## The statisticians and computer scientists point-of-view

The statistical perspective of machine learning frames data in the context of a hypothetical function (f) that the machine learning algorithm aims to learn. Given some input variables (Input)  the function answer the question as to what is the predicted output variable (Output).

Output = f(Input)

The inputs and outputs can be referred to as variables or vectors.

The computer science perspective uses a row of data to describe an entity (like a person) or an observation about an entity. As such, the columns for a row are often referred to as attributes of the observation and the rows themselves are called instances.

## The underlying assumption

There is a common principle that underlies all supervised machine learning algorithms for predictive modeling.
Machine learning algorithms are described as learning a target function (f) that best maps input variables (X) to an output variable (Y).

Y = f(X)

This is a general learning task where we would like to make predictions in the future (Y) given new examples of input variables (X). We don't know what the function (f) looks like or its form. If we did, we would use it directly and we would not need to learn it from data using machine learning algorithms.

The most common type of machine learning is to learn the mapping Y = f(X) to make predictions of Y for new X. This is called predictive modeling or predictive analytics and our goal is to make the most accurate predictions possible.

## Parametric vs. non-parametric algorithms

what is a parametric machine learning algorithm and how is it different from a nonparametric machine learning algorithm?

Assumptions can greatly simplify the learning process, but can also limit what can be learned. Algorithms that simplify the function to a known form are called parametric machine learning algorithms.

The algorithms involve two steps:

Select a form for the function.
Learn the coefficients for the function from the training data.
Some examples of parametric machine learning algorithms are Linear Regression and Logistic Regression.

Algorithms that do not make strong assumptions about the form of the mapping function are called nonparametric machine learning algorithms. By not making assumptions, they are free to learn any functional form from the training data.

Non-parametric methods are often more flexible, achieve better accuracy but require a lot more data and training time.

Examples of nonparametric algorithms include Support Vector Machines, Neural Networks and Decision Trees.

## Cross-Validation

our goal with applied machine learning is to develop a model to make predictions on new data.

That is, given new inputs like an unlabeled photo or a day of the week, we want to know if it is a picture of a dog or the estimated sales figures.

We want predictions.

On a project, we:
Try lots of data preparation schemes in order to best present the signal in the underlying problem to the learning algorithms.
We try suites of learning algorithms to best capture the relationship between the input and the outputs.
And we use resampling methods like train-test splits and k-fold cross validation to estimate the skill of models when making predictions on new data.
It is only after we have chosen our best combination of data prep, algorithm, and configurations that we can train a final model on all available data and start actually making predictions on unseen data.

New practitioners in the field often confuse the steps of resampling and model finalization asking questions like:

How do I make predictions with cross validation?
or
Which cross-validation model do I keep?

This is not surprising as the literature almost universally does not talk about it.

I hope this note has made things clearer for you. You can learn more in my post:

[How to Train a Final Machine Learning Model](http://machinelearningmastery.com/train-final-machine-learning-model/)


## Bias and Variance Trade-Off

Machine learning algorithms can best be understood through the lens of the bias-variance trade-off.

Bias are the simplifying assumptions made by a model to make the target function easier to learn.

Generally, parametric algorithms have a high bias making them fast to learn and easier to understand but generally less flexible. In turn, they have lower predictive performance on complex problems that fail to meet the simplifying assumptions of the algorithms bias.

Decision trees are an example of a low bias algorithm, whereas linear regression is an example of a high-bias algorithm.

Variance is the amount that the estimate of the target function will change if different training data was used. The target function is estimated from the training data by a machine learning algorithm, so we should expect the algorithm to have some variance, not zero variance.

The k-Nearest Neighbors algorithm is an example of a high-variance algorithm, whereas Linear Discriminant Analysis is an example of a low variance algorithm.

The goal of any predictive modeling machine learning algorithm is to achieve low bias and low variance. In turn, the algorithm should achieve good prediction performance. The parameterization of machine learning algorithms is often a battle to balance out bias and variance.

- Increasing the bias will decrease the variance.
- Increasing the variance will decrease the bias.


## Linear regression

Linear regression is perhaps one of the most well-known and well-understood algorithms in statistics and machine learning.

Isn't it a technique from statistics?

Predictive modeling is primarily concerned with minimizing the error of a model or making the most accurate predictions possible, at the expense of explainability. We will borrow, reuse and steal algorithms from many different fields, including statistics and use them towards these ends.

The representation of linear regression is an equation that describes a line that best fits the relationship between the input variables (x) and the output variables (y), by finding specific weightings for the input variables called coefficients (B).

For example:

y = B0 + B1 * x

We will predict y given the input x and the goal of the linear regression learning algorithm is to find the values for the coefficients B0 and B1.

Different techniques can be used to learn the linear regression model from data, such as a linear algebra solution for ordinary least squares and gradient descent optimization.

Linear regression has been around for more than 200 years and has been extensively studied. Some good rules of thumb when using this technique are to remove variables that are very similar (correlated) and to remove noise from your data, if possible.

It is a fast and simple technique and good first algorithm to try.
