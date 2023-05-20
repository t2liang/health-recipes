# How Do "Healthy" Recipes Compare to "Unhealthy" Ones, According to Reviewers
UCSD data science DSC80 course analysis project.
---
layout: page
title: Project 3

---
## Introduction

In recent years, media and health professionals have promoted a shift to healthier foods, with lower carbs, lower fat, lower sugar, etc. But how do people rate these healthier recipes in comparison to their counterparts? 

## Cleaning and EDA

## Data Cleaning 
|    | name                                 |     id |   minutes |   contributor_id | submitted   |
|---:|:-------------------------------------|-------:|----------:|-----------------:|:------------|
|  0 | 1 brownies in the world    best ever | 333281 |        40 |           985201 | 2008-10-27  |
|  1 | 1 in canada chocolate chip cookies   | 453467 |        45 |          1848091 | 2011-04-11  |
|  2 | 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  |
|  3 | 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  |
|  4 | 412 broccoli casserole               | 306168 |        40 |            50969 | 2008-05-30  |


### Univariate Analysis

<iframe src="assets/histplot.html" width=700 height=600 frameBorder=0></iframe>
The above graph depicts the distribution of the values of 'total fat' for every recipe in the dataset. Visually, it follows that a large majority of data within the dataset are on recipes with low calorie values. 

### Bivariate Analysis

<iframe src="assets/scatter.html" width=700 height=600 frameBorder=0></iframe>
The above graph depicts association between 'rating' and 'calories'. Looking at the data, we can infer based off of outlier points that recipes with calorie value higher than average are corelated with higher rating.


## Assessment of Missingness

### NMAR Analysis

Within the dataset, the "review" feature is likely to be NMAR. Each "review" data feature within our population represents a self-reported submission by users of the site. "Rating" and "Review" are the only features that are dependent on the input of the user, and not data provided from the recipe site itself. Therefore, it is reasonable to infer that a missing review suggests a user choosing not to write a written review or some other means occured that omitted the user's review. In other words, the missingness of the review value depends on the value itself. 

### Missingness Dependency

## Hypothesis Testing
* Null Hypothesis: In the population, the average rating of recipes labeled “healthy” and  recipes not labeled “healthy” have the same distribution – the lower average rating of recipes with the “healthy” tag is due to chance alone.
In other words, if we picked 16024 reviews randomly from the population, it is reasonable to see an average this low.
That is, if we repeatedly sampled groups of 16024 reviews from the population and computed their mean average rating, it would not be uncommon to see an average  this low.
there are two samples:
    - Average rating of “healthy” recipes
    - Average rating of non “healthy” recipes


* Alternative Hypothesis: In the population, recipes labeled “healthy” have a lower average rating than recipes not labeled “healthy” – the lower average rating of recipes with the “healthy” tag is not due to chance alone.
* Test Statistic: mean average rating.

Using a permutation test, we depicted a p-value of 0.0, telling us that there is a near impossible chance for us to witness a difference greater than or equal to the one we observed between the average rating of “healthy” recipes and non “healthy” recipes. Thus, we can reject the null hypothesis with a significance level of 0.05 in favor of the alternative that "healthy" recipes on average are rated lower than those without the "healthy" tag.




