---
title: 'Activity B' 
linktitle: 'Activity B'
toc: true
type: docs
date: "2019-06-05T00:00:00-07:00"
draft: false
menu:
  302:
    weight: 313
    parent: "Assignments"
    identifier: "activityB"
    name: "Activity B"


# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 313
---



---

# Activity B Description

This activity explores **correlation** *and* to learn how to create a scatterplot using R. 

---

# The Data

Using content from [this website](http://highered.mheducation.com/sites/dl/free/0078110394/586020/correlation.html) (note that we're using RStudio, not Excel), here is the context for this activity:

> A researcher was interested in whether there was an association between communication skills and quality of peer relationships in third grade classrooms. Teachers in each class completed a communicative skills checklist and a rating scale of peer relations for each child. The items for each scale were averaged to provide an overall score for each child.

You'll need to use this **[correlation.csv](correlation.csv)** data for your assignment.

Variable names:

1. `ID` = case identification number
1. `comm` = communication skills
1. `peers` = quality of peer relations

---

## Steps to completion

Import the data using whatever method you prefer, either the code below or the **Import Dataset** option in the **Environment** tab. It's easiest to simply use the code below as it will point to the file on the server, taking its location out of the equation for your own code.

Protip: load this data frame as **dfb** (it's the data for Activity B, so... **dfb** but, really, you can call it whatever you like) and create values for the variables using the following commands:


```r
dfb <- read.csv(url("https://302.ryanstraight.com/correlation.csv"), header = TRUE)
comm <- dfb$comm
peers <- dfb$peers
```

Install the **[summarytools](https://github.com/dcomtois/summarytools)** and **[ggplot2](https://ggplot2.tidyverse.org/)** plugins in RStudio. This is the one we looked at while reviewing Activity A's solutions.

### Watch

+ [Scatterplot in RStudio](https://www.youtube.com/watch?v=A9hAp9AGc0s)

>{{< youtube A9hAp9AGc0s >}}

+ [How to make a scatterplot in R (with regression line)](https://www.youtube.com/watch?v=cGb5iqhf0NU)

>{{< youtube cGb5iqhf0NU >}}

+ [Plotting with ggplot2](https://www.youtube.com/watch?v=HeqHMM4ziXA) to get the basics on how to produce the plots you need below.

>{{< youtube HeqHMM4ziXA >}}

## Assignment

This activity goes well beyond simply displaying frequencies and descriptives for common concepts like means and medians. You will need to dig around the R documentation for the commands to best answer the questions below. For this activity, create and submit a document that includes *and answers* the following:

1. A **scatterplot** that displays the relationship between the **peers** and **comm** variables. Answer the following:
    1. What does this chart tell you about the relationship between the two variables?
    1. What direction is this association?
    1. How did you determine this?
    1. If you had to identify the association, would you label is *small*, *moderate*, or *strong*? Why?
1. Determine the *Pearson correlation* for the **peers** and **comm** variables.
    1. Interpret this number.
    1. What is the strength of the association?
    1. What is the direction?
    1. Like the scatterplot above, do you think it is small, moderate, or strong? 
    1. How does your interpretation of the Pearson correlation coefficient compare to that of the scatterplot?
1. Determine $ r^{2} $
    1. Compute the square of the correlation coefficient you previously calculated. 
    1. Interpret this value. What does it indicate about the association?
    1. Write a statement about the meaning of the R-squared ($ r^{2} $) value in terms of the variables.
    1. How does $ r^{2} $ compare to what you saw in the scatterplot and the Pearson correlation coefficient?
    1. Do you think this is a more valuable statistic? Why?



---

# Results

Your RStudio results should look like the following. I've displayed the R code chunks before the results.

## Descriptives

First, let's get some descriptives of the data. Remember that `ID` is simply a case identifier and isn't important for this.


```r
library(summarytools)
descr(dfb, style = "rmarkdown")
```

### Descriptive Statistics  

|          &nbsp; |   comm |     ID |  peers |
|----------------:|-------:|-------:|-------:|
|        **Mean** |   5.01 | 100.50 |   4.82 |
|     **Std.Dev** |   1.61 |  57.88 |   1.27 |
|         **Min** |   1.00 |   1.00 |   1.00 |
|          **Q1** |   4.00 |  50.50 |   4.00 |
|      **Median** |   5.00 | 100.50 |   4.80 |
|          **Q3** |   6.50 | 150.50 |   5.80 |
|         **Max** |   7.00 | 200.00 |   7.00 |
|         **MAD** |   1.85 |  74.13 |   1.33 |
|         **IQR** |   2.50 |  99.50 |   1.80 |
|          **CV** |   0.32 |   0.58 |   0.26 |
|    **Skewness** |  -0.48 |   0.00 |  -0.38 |
| **SE.Skewness** |   0.17 |   0.17 |   0.17 |
|    **Kurtosis** |  -0.71 |  -1.22 |  -0.15 |
|     **N.Valid** | 200.00 | 200.00 | 200.00 |
|   **Pct.Valid** | 100.00 | 100.00 | 100.00 |


## Scatterplot

Using the simple RStudio **plot** command:


```r
plot(comm, peers,                         # plot the variables 
  xlab="Communication",                   # x axis label 
  ylab="Peer relationships")              # y axis label
  abline(lm(comm ~ peers))                # draw the trend line
```

<img src="/academic-kickstart/courses/302/313-activityB_files/figure-html/scatterplot-1.png" width="672" />

Using the more enjoyable **ggplot2** command that provides a nicer looking scatterplot *and* confidence intervals around the trend line:


```r
library(ggplot2)
ggplot(dfb, aes(x=comm, y=peers)) +
  geom_point(shape=1) +
  geom_smooth(method=lm)
```

<img src="/academic-kickstart/courses/302/313-activityB_files/figure-html/ggplot2-1.png" width="672" />

## Correlations

Pearson's correlation coefficient: 0.5194169


```r
cor(comm, peers)
```

```
## [1] 0.5194169
```

## $ r^{2} $

To determine the $ r^{2} $ we'll need to examine the coefficients a bit more closely. It's easier if we create an object in RStudio to do just that:


```r
model1 <- lm(comm~peers)
summary(model1)
```

```
## 
## Call:
## lm(formula = comm ~ peers)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -4.4562 -0.9695  0.1863  1.0161  2.9949 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)  1.82838    0.38462   4.754 3.84e-06 ***
## peers        0.65961    0.07712   8.553 3.26e-15 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 1.383 on 198 degrees of freedom
## Multiple R-squared:  0.2698,	Adjusted R-squared:  0.2661 
## F-statistic: 73.16 on 1 and 198 DF,  p-value: 3.258e-15
```
