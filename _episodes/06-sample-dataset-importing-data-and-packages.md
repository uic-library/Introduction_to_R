---
title: "sample dataset and importing data in R studio"
time: 0
objectives:
- " learning how to use the sample dataset"
- "understanding how to import data in R studio"

keypoints:
- ""
---

## Sample Dataset 

-	One of the easiest ways to start experimenting with the analysis in R is by means of built-in sample datasets available in R. These datasets are available in their own package. 

-	Use the code provided in the script to load the dataset and then toggle through help function to know the complete information of the dataset.

~~~

# INSTALL AND LOAD PACKAGES ################################

# Load base packages manually
library(datasets) # For example datasets
?datasets
library(help = "datasets")

# SOME SAMPLE DATASETS #####################################

iris
?iris

cars <-cars

head(cars)

iris <- iris
head(iris)

tail(iris,20)

iris[,c(1,2)]

iris[,c('Sepal.Length')]


str(iris)

rm(list = ls())

iris

# CLEAN UP #################################################

# Clear environment
rm(list = ls()) 

# Clear packages
detach("package:datasets", unload = TRUE)  # For base

# Clear plots
dev.off()  # But only if there IS a plot

# Clear console
cat("\014")  # ctrl+L

~~~
{: .language-r}


### Importing data 
There are multiple commands with various arguments to import data from different file formats into R environment. I shall show the simplest command to import a csv file as a data frame 

data_frame_name <- read.csv(file. choose(), header = T)

Here, file. choose() - Allows you to choose a .csv file stored in your local desktop

Here, header = T - Indicates the first row in the file contains column names.

![importing data](../fig/06-importing-data.PNG)


Double click (or) click once and select open on your desired file to import 

Once the data has been imported successfully the data frame would be visible with its name in the Environment pane on the top right.

### Packages 

-	One of the most important things in R is its collection of Packages. The package is a collection of R functions, data, and compiled code and Library is the location where the packages are stored. In order to access these packages, we can either go to **r-project. Org > CRAN> 0 Cloud> packages>CRAN task view** or use the **command library()** to load the package in the current R session.
-	Then just call the appropriate package functions 

install.packages("package_name") – Install the package from CRAN repository 

install.packages( c("package_1", “"package_2", "package_3") ) -Install multiple packages

library("package_name") – Load the package in current R session.

~~~
# first step of using a package
install.packages("tidyverse")

# second step - needs happen each session
# load library
library(tidyverse)

## load data from elsewhere

df <- read_csv("data/StateData.csv")

~~~
{: .language-r}









