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

## Activity B Description

This activity explores **correlation** *and* to learn how to create a scatterplot using R. 

---

## The Data

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


