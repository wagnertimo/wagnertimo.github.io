---
published: true
title: R and Jupyter Notebook – Installation
layout: post
---

[Jupyter Notebook](http://jupyter.org) is a server-client application that allows editing and running notebook documents via a web browser. Notebook documents are documents produced by Jupyter Notebook which contain both computer code (e.g. python) and rich text elements (paragraph, equations, figures, links, etc.). They are both human-readable documents containing the analysis description and the results (figures, tables, etc.) as well as executable documents which can be run to perform data analysis.
A notebook kernel is a computational engine that executes the code contained in a notebook document. The ipython kernel executes python code and the IRkernel runs R code which will be used later. But there are also kernels for many other languages.


### Get R working in the Jupyter Notebook

**Step 1:** Installation of the anaconda package.

Download the newest [anaconda installer](https://www.continuum.io/downloads). You can choose between the graphical interface or the command line version for installation.



**Step 2:** Install the IRkernel.

After downloading and installing anaconda, you need to install the IRkernel. This will do anaconda for you. Just type the following command in the terminal.
```sh
conda install -c r ipython-notebook r-irkernel
```



**Step 3:** Install required R packages.

Now you need some additional R packages to get everything running. Open RStudio or any other IDE and type in the following command in the console.
```r
install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest'))
devtools::install_github('IRkernel/IRkernel') 
```


**Step 4:** Loading the IRkernel.
After installing the packages, you have to load the IRkernel. Therefore call the `installspec()` function of the IRkernel package in the R console.
```r
IRkernel::installspec()
```


**Step 5:** Install the Essentials.
Before you are able to run R in Jupyter Notebook, you will need some essentials to be installed. Use again the `conda`command in the shell.
```sh
conda install -c r r-essentials
```


**Step 6:** Launch Jupyter Notebook.
Now you should be able to open Jupyter Notebook and select R as the notebook kernel.
```sh
jupyter notebook
```
A session should start in your terminal and automatically open the browser with Jupyter Notebook. You can create a new file by selecting the *New* button and choosing R as the Notebook.
