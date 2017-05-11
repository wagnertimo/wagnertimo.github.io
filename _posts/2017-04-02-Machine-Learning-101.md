---
published: false
comments: true
layout: post
title: Machine Learning 101 - The Basics
---
This is my first blog post on my new blog. I decided to host it on GitHubs Pages. It is more convenient since I am already working with Git.

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
