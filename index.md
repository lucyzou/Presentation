---
title       : Presentations about my prediction App
subtitle    : A app for wage prediction
author      : ZouXia
job         : Student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Description of the App

It is a simple App that can help people to predict their wage according to their age,education level,marriage status and type of job you have.  The rationale behind it come from the meachine learning. And the training data is Wage dataset come from ISLR package. And the method use to fit the data is lm

--- .class #2 

## Prediction Model

```r
library(ISLR)
library(caret)
data(Wage)
modelfit<-train(wage~age+education+maritl+jobclass,method="lm",data = Wage)
```

--- .class #3


## Summary of the Model

```r
summary(modelfit)
```

```
## 
## Call:
## lm(formula = .outcome ~ ., data = dat)
## 
## Residuals:
##      Min       1Q   Median       3Q      Max 
## -109.630  -19.235   -3.303   14.543  217.670 
## 
## Coefficients:
##                               Estimate Std. Error t value Pr(>|t|)    
## (Intercept)                   56.88532    3.19666  17.795  < 2e-16 ***
## age                            0.30541    0.06272   4.869 1.18e-06 ***
## `education2. HS Grad`         11.20924    2.43099   4.611 4.18e-06 ***
## `education3. Some College`    23.43119    2.57044   9.116  < 2e-16 ***
## `education4. College Grad`    37.89354    2.57429  14.720  < 2e-16 ***
## `education5. Advanced Degree` 61.45169    2.83020  21.713  < 2e-16 ***
## `maritl2. Married`            18.64946    1.75936  10.600  < 2e-16 ***
## `maritl3. Widowed`             1.76970    8.26158   0.214 0.830399    
## `maritl4. Divorced`            5.16183    2.97367   1.736 0.082694 .  
## `maritl5. Separated`          12.36977    5.00287   2.473 0.013471 *  
## `jobclass2. Information`       4.73709    1.35342   3.500 0.000472 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 35.14 on 2989 degrees of freedom
## Multiple R-squared:  0.2932,	Adjusted R-squared:  0.2909 
## F-statistic:   124 on 10 and 2989 DF,  p-value: < 2.2e-16
```

--- .class #4

## Predictos
   As mentioned above, the predictors include your age,education level,marriage status and type of job you have.
More specifically.

 1.Age is the age of the workers.

 2.Education is a factor level it include  1. < HS Grad 2. HS Grad3. Some College 4. College Grad and 5. Advanced Degree. 

 3.Maritl is also a factor include 1. Never Married 2. Married 3. Widowed 4. Divorced and 5. Separated.

 4.Jobclass is a factor include  1. Industrial and 2. Information.

--- .class #5
