---
published: true
title: Jupyter Notebook – Using R
excerpt: "Extend Jupyter Notebook with R."
image:
  feature: jupyterR.svg
layout: post
comments: true
categories: [R, Jupyter Notebook]
---

You can use the programming language `R` in Jupyter Notebook by installing the `IRkernel`.
A notebook kernel is a computational engine that executes the code contained in a notebook document. The `ipython kernel` executes python code and the `IRkernel` runs R code which will be used later. But there are also kernels for many [other languages](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels).


Firstly, you need to install the latest anaconda package. If you haven't done this before, walk through my post [Jupyter Notebook – Installation](../2017-04-02-Jupyter-Notebook-Installation).

Now you can get R working in Jupyter notebook by following simple command lines.

**Step 1:** Install the IRkernel.

After downloading and installing anaconda, you need to install the IRkernel. This will do anaconda for you. Just type the following command in the terminal.
```sh
conda install -c r ipython-notebook r-irkernel
```


**Step 2:** Install required R packages.

Now you need some additional R packages to get everything running. Open RStudio or any other IDE and type in the following command in the console.
```r
install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest'))
devtools::install_github('IRkernel/IRkernel') 
```


**Step 3:** Loading the IRkernel.

After installing the packages, you have to load the IRkernel. Therefore call the `installspec()` function of the IRkernel package in the R console.
```r
IRkernel::installspec()
```


**Step 4:** Install the Essentials.

Before you are able to run R in Jupyter Notebook, you will need some essentials to be installed. Use again the `conda`command in the shell.
```sh
conda install -c r r-essentials
```


**Step 5:** Launch Jupyter Notebook.

Now you should be able to open Jupyter Notebook and select R as the notebook kernel.
```sh
jupyter notebook
```
A session should start in your terminal and automatically open the browser with Jupyter Notebook. You can create a new file by selecting the *New* button and choosing R as the Notebook.
