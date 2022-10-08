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

### Data Visulaistion using the basic Plot function  in R 
The most used plotting function in R programming is the plot() function. It is a generic function, meaning, it has many methods which are called according to the type of object passed to plot(). In the simplest case, we can pass in a vector and we will get a scatter plot (default) of magnitude vs index. But generally, we pass in two vectors and a scatter plot of these points are plotted.
For example, the command plot(c(1,2),c(3,5)) would plot the points (1,3) and (2,5)
In the exercise below we will see how to create a generic plot, bar chart and a histogram in R using the Sample dataset available in the Program

#### PLOT FUNCTION IN R

~~~
LOAD DATASETS PACKAGES ###################################

library(datasets)  # Load/unload base packages manually

LOAD DATA ################################################

head(iris)

PLOT DATA WITH PLOT() ####################################

?plot  # Help for plot()

plot(iris$Species)  # Categorical variable
plot(iris$Petal.Length)  # Quantitative variable
plot(iris$Species, iris$Petal.Width)  # Cat x quant
plot(iris$Petal.Length, iris$Petal.Width)  # Quant pair
plot(iris)  # Entire data frame

Plot with options
plot(iris$Petal.Length, iris$Petal.Width,
  col = "#cc0000",  # Hex code for datalab.cc red
  pch = 19,         # Use solid circles for points
  main = "Iris: Petal Length vs. Petal Width",
  xlab = "Petal Length",
  ylab = "Petal Width")

PLOT FORMULAS WITH PLOT() ################################

plot(cos, 0, 2*pi)
plot(exp, 1, 5)
plot(dnorm, -3, +3)

Formula plot with options
plot(dnorm, -3, +3,
  col = "#cc0000",
  lwd = 5,
  main = "Standard Normal Distribution",
  xlab = "z-scores",
  ylab = "Density")
  ~~~
{: .language-r}


#### Plotting Bar Chart in R 
  
~~~
 
library(datasets)

LOAD DATA ###############################################
?mtcars
head(mtcars)

sort.default(mtcars, decreasing = TRUE)

BAR CHARTS ###############################################

barplot(mtcars$cyl)             # Doesn't work

Need a table with frequencies for each category
cylinders <- table(mtcars$cyl)  # Create table
barplot(cylinders)              # Bar chart
plot(cylinders)                 # Default X-Y plot (lines)

CLEAN UP #################################################

Clear environment
rm(list = ls()) 

Clear packages
detach("package:datasets", unload = TRUE)  # For base

Clear plots
dev.off()  # But only if there IS a plot

Clear console
cat("\014")  # ctrl+L

~~~
{: .language-r}


#### Plotting Historgram in R 

~~~

LOAD PACKAGES ############################################

library(datasets)

LOAD DATA ################################################

?iris
head(iris)

BASIC HISTOGRAMS #########################################

hist(iris$Sepal.Length)
hist(iris$Sepal.Width)
hist(iris$Petal.Length)
hist(iris$Petal.Width)

HISTOGRAM BY GROUP #######################################

Put graphs in 3 rows and 1 column
par(mfrow = c(3, 1))

Histograms for each species using options
hist(iris$Petal.Width [iris$Species == "setosa"],
  xlim = c(0, 3),
  breaks = 9,
  main = "Petal Width for Setosa",
  xlab = "",
  col = "red")

hist(iris$Petal.Width [iris$Species == "versicolor"],
  xlim = c(0, 3),
  breaks = 9,
  main = "Petal Width for Versicolor",
  xlab = "",
  col = "purple")

hist(iris$Petal.Width [iris$Species == "virginica"],
  xlim = c(0, 3),
  breaks = 9,
  main = "Petal Width for Virginica",
  xlab = "",
  col = "blue")

Restore graphic parameter
par(mfrow=c(1, 1))

CLEAN UP #################################################

Clear packages
detach("package:datasets", unload = TRUE)  # For base

Clear plots
dev.off()  # But only if there IS a plot

Clear console
cat("\014")  # ctrl+L

Clear mind :)

~~~
{: .language-r}



This brings us to an end of this workshop however the reference section provides links to all the materials used in this workshop and links which provide more 
detailed understanding of Each Package in R.
















