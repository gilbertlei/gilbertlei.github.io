---
layout: post
title: Statistics for Data Science (III)
---

In this blog, I am going to summarize linear regression.

- A regression analysis is used to model the relationship between a dependent variable and one or more independent variables.
- independent variables are also called `explanatory variables`, `covariates`, `predictors`.
- The most common regression is linear regression.

## R functions related to linear regression  
- **t.test()**, can be used to analyze only two samples
  ```
  # test whether the means of category 1 and category 2 are equal
  t.test(category_1_data, category_2_data, var.equal=T)  	
  ```
  ![](../images/stats/t-test-example2.png)  
- **aov()**, ANOVA test, can be used to analyze two or more samples.   
  ```
  # test whether the mean values are equal
  # if there is only one independent_variable and only two groups in this independent_variable,
  # this ANOVA test is the same as t-test
  summary(aov(dependent_variable ~ independent_variables, data = sample_data))
  ```
  ![](../images/stats/anova-example.png)  

- **lm()**, can be used to analyze two or more samples
  ```
  # test whether the means are equal
  lm(dependent_variable ~ independent_variables, data=sample_data)
  # use broom::tidy() to tidy output from lm()
  broom::tidy(lm(value~factor, data=sample_data))
  ```
  ![](../images/stats/lm-example.png)  

## ANOVA explained
- MSB: mean squares between  
![](../images/stats/MSB.JPG)  
- MSW: mean squares within  
![](../images/stats/MSW.JPG)  
- F statistic  
![](../images/stats/F-statistic.JPG)   
note: F statistic follows F distribution.  
![](../images/stats/F-distribution.JPG)

## lm() explained  

Suppose we want to model the relationship between house prices and house ages (two-level factor) and house sizes. We will consider the interaction between house ages and house sizes. A lm() function will generate a vector of parameters contains:  
- *age_factor_C*     # this is the intercept of C. also called 'reference'  
- *age_factor_O*     # this is the change of intercept due to different age factor (O vs. C). also called 'treatment effect'. it measures the difference in sample means  
- *size_C*           # this is the slope of size for C   
- *size_O*           # this is the change of slope due to different age factor (O vs. C)   

Tests are always testing that the parameters (β0, β1, …) equal to zeros. Example:
![](../images/stats/lm-example-2.JPG)  
When we do not consider the interaction between parameters, there will be only one slope. example:
![](../images/stats/lm-example-3.JPG)  

## Use Linear Model in Estimation/Inference  
A typical linear model looks like this:  
![](../images/stats/linear-model.JPG)  
We use linear regression to estimate population parameters and also forecast *y* based on new *x*.  
![](../images/stats/lm-example-4.JPG)  
- **confidence interval of intercept**   
![](../images/stats/ci-of-intercept.JPG)  
- **confidence interval of slope**   
![](../images/stats/ci-of-slope.JPG)  

- **Confidence interval** of the prediction: the confidence interval for population mean   
![](../images/stats/ci-of-prediction.JPG)  
we can use *lm()* function to generate confidence interval of the prediction  
![](../images/stats/lm-confidence-interval.JPG)
- **Prediction interval**: the confidence interval for new point estimates  
![](../images/stats/prediction-intervals.JPG)  
![](../images/stats/prediction-intervals-2.JPG)  
we can use *lm()* function to generate prediction intervals.
![](../images/stats/lm-prediction-interval.JPG)


## How to Measure the Goodness of Fit  
One important measurement is the `coefficient of determination`  
![](../images/stats/lm-goodness-of-fit.JPG)    

![](../images/stats/lm-R-square.JPG)  
- in above equation, SS_Total stands for the sum of squared error of an intercept-only model.  
- because R^2 unnecessarily increases with additional explanatory variables, statistician created adjusted R^2, which takes into account the size of the model so that the index won't be skewed due to additional explanatory variables.  

![](../images/stats/lm-adj-R-square.JPG)  

Because R^2 does not have a known distribution so we can not use it to test the hypothesis that our full model is better than an intercept-only model. Statistician came out with a F-statistic.  
![](../images/stats/lm-F-statistic.JPG)  
- with F-statistic, we can run F-test to test relevant hypothesis.  
