This page is for ML practitioners to share best practices on designing experiment workflows, to make experiments **fast**, **generalizable**, and **incremental**. 

This is **not** intended to give ideas on things to try out (for that, check out the [Modeling checklist](https://wiki.thinkingmachin.es/s/mlchecklist)).

[TOC]

# Fast
> Do not ever allow calculations to exceed 10 seconds while you work on a problem - [How to Do ML Efficiently](https://medium.com/hackernoon/doing-machine-learning-efficiently-8ba9d9bc679d)
## Sampling
How do I pick the right small dataset to explore/prototype on?

* How large should it be? 
    * 1%, 10% as long as it's representative
* When is it not ok to use random?
    * When the data's sequential 
        * Illustration: [This article](https://www.fast.ai/2017/11/13/validation-sets/), Section on *When is a random subset not good enough?*
    * When you have imbalanced data (e.g. fraud)
* How do I make sure the sample contains all the values?
    * [Compare distributions per variable of sample vs full dataset](https://medium.com/data-science-reporter/how-to-correctly-select-a-sample-from-a-huge-dataset-in-machine-learning-24327650372c)
        1. Take one variable from the sample
        1. Compare its probability distribution with the probability distribution of the same variable of the population
        1. Repeat with all the variables
        1. Keep generating random samples until all the p-values are greater than the minimum allowed confidence level

Check that sample has same distribution
* Overlapping histograms plot (like the ones from [Unistar POC](https://colab.research.google.com/drive/1Fs1rAhZNpWpSrAkbJpgxPhbKlU_3xRYf#scrollTo=AOMwDhBUmTOu&forceEdit=true&sandboxMode=true))
* Comparing using Statistical tests
    * Categorical - Pearson's Chi-Square
    * Numerical - KS test


## Prioritizing experiments
In order of ***try first***:
1. Simple model - Linear Regression ([Lasso](https://hackernoon.com/practical-machine-learning-ridge-regression-vs-lasso-a00326371ece))
2. Try trees, svms - sklearn out of the box
3. Add more data
4. Add more features
5. Hyperparam tuning
6. Try neural nets - because this takes a while

**(Prioritized) Steps to Avoid Overfitting** from fastai
![](https://storage.googleapis.com/tm-codimd/uploads/upload_08dc9150f64bd02219c38aeb6c2ec2c4.png)

**Ceiling Analysis** from Machine Learning by ANg
aka if this component had 100% accuracy how much will the system accuracy improve
![](https://storage.googleapis.com/tm-codimd/uploads/upload_b2661345f5868af5d29085534c10f1e9.png)


# Generalizable

## Hypothesis testing
From Machine Learning Yearning:
![](https://storage.googleapis.com/tm-codimd/uploads/upload_1f98ec26554f05be6268c6bdb9917b4d.png)

Is the result of my experiment by chance?

Apply on different samples of the data
1. Make new sample
1. Apply baseline treatment to sample
1. Apply experiment treatment
1. Repeat for more samples
1. Check results of baseline vs experiment as distributions

## Cross validation
* KFold
* Time Series Split - hold out by period
* Geospatial CV - holdout test area

## No Data Leakages
* Duplicates
* Using future data
* Including predicted value in calculating aggregate feature

## Reproducible Environment
* Set the seed
* Run notebook from top to bottom (should be fast because of sampling)
* Create requirements.txt

[ML Reproducibility Checklist](https://www.cs.mcgill.ca/~jpineau/ReproducibilityChecklist.pdf)

# Incremental
## Well-documented
Keeping track of experiments
[[Machine Learning Operations (MLOps)]]
**Hypothesis Driven Workflow** from [How to Do Good Research](https://docs.google.com/presentation/d/1A6C_6cIfkDEQ2PWP0Udx761pmpziJKOxZXR2iWQ9G6A/edit#slide=id.g62b0006b7b_0_0)
* Tools
    * WandB
    * MLFlow
    * DVC
    * [Others](https://neptune.ai/blog/best-ml-experiment-tracking-tools)

## Scalable
Once the experiment is ok, how hard is it to apply to a larger dataset?
* Consider the number of operations involved aka [Time complexity](https://towardsdatascience.com/time-complexity-for-data-scientists-664d00e57724)
* Timing tools - %%time




