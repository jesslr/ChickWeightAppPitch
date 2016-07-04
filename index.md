---
title       : Chick Weights by Diet
subtitle    : Explore effect of diet on chick weight
author      : Jessica L. Ramos
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

My shiny application uses the ChickWeight R dataset. This dataset contains the body weights of chicks measured at birth and every second day until day 20.  They were also measured on day 21.  The experiment evaluated 4 different protein diets to see which had the most effect on chick weight.  

Here is a sample of what the data look like:

```r
head(ChickWeight)
```

```
##   weight Time Chick Diet
## 1     42    0     1    1
## 2     51    2     1    1
## 3     59    4     1    1
## 4     64    6     1    1
## 5     76    8     1    1
## 6     93   10     1    1
```

--- .class #id 

## User input

My shiny application takes two user inputs:

* Diet
    - drop down selection box allows you to choose one of the four diets 
* Linear regression line
    - checkbox will plot a linear regression line on the scatterplot

Here is a screenshot from the app showing the user inputs: 

<div style='text-align: center;'>
    <img height='300' src='./assets/img/InputScreenshot.png' />
</div>

---

## Reactive output

My shiny application shows a scatterplot of Weight and Age in Days for the diet selected by the user.  It will include a linear regression line if the user checks the box to show one.  For example, here is the plot for diet 1, with regression line:

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png)

---

## Reactive outputs

The app will also show the mean weight and standard deviation for the diet selected:

```r
avgWt <- round(mean(subData$weight, na.rm=TRUE), 2)
sDev <- round(sd(subData$weight, na.rm = TRUE), 2)
```
For instance, the mean weight, calculated above for diet 1 is 102.65 and the standard deviation is 56.66.

## Conclusion
This is a simple application that may not hold much practical use, but it serves as an introduction to shiny and slidify.

To access my shiny app, please visit the following link:
https://jessielr.shinyapps.io/ChickWeight/







