---
layout: posts
title:  "Basic logistic regression"
date:   2022-04-25 00:00:00 -0400
categories: jekyll update
author_profile: true
author: "Sarah Wesolowski, PhD"
---

**Logistic regression** (logit) is a nonlinear method that is typically used for classification tasks, which can be binary (true/false) or multi-class. It is popular because the math is elegant and looks kind of similar to linear regression. Popular it may be, but it's up to the practitioner (you) to judge whether it makes sense for your classification problem.

In this short article, I will focus on the **basics of binary logit from a math+coding point of view**, with short code snippets in `Python`. There are lots of articles and descriptions of logit out there, but I'm writing this because how it works (e.g., the equations and math stuff) are often left out of the discussion.

## Notation

- **Outcome (response)**: Let the binary outcome of interest be denoted as \\( Y=\{0,1\} \\), where conventionally 0 is the false case and 1 is the true case.
- **Measurements (instances)**: We have \\(N\\) measurements denoted with index \\( i \\) (patients, cases, locations, etc.) consisting of an outcome \\( Y_i \\) and the a set of predictors \\(\mathbf{X}_i\\).
- **Features (predictors)**: Let there be \\( p \\) predictors \\( \{X_1, X_2, \ldots, X_p\}\\) that represent the types of data we have available. For a single instance, we denote the predictors by the length \\(p\\) vector \\( \mathbf{X} \\).
- **Probability**: The quantity \\( P(w\|z) \\) is read as the probability of w being true, given z.


### Note on assumptions

We are assuming here that for each \\(i\\)th instance in the dataset, there is no missing-ness in the measurements and that there is only a single univariate outcome \\(y_i\\). In real data sets, one would expect that the initial data must be cleaned to deal with missing values, outliers, and other possible issues before getting to the stage of actually using logistic regression.

## Basic logit model

Logistic regression (and probit) for binary classification can be motivated by a nonlinear probability model. *This just means that the output of the model, the probability of success or failure, isn't directly related to a straight-line type equation*.

### Odds Ratio

The quantity of interest in this model is the *odds* or *odds ratio*

$$ \frac{P(Y=1\|\mathbf{X})}{P(Y=0\|\mathbf{X})} = \frac{P(Y=1\|\mathbf{X})}{1-P(Y=1\|\mathbf{X})} $$

The odds ratio is a fraction that indicates how often something happens relative to how often it does not happen. The odds ratio takes on values from 0 to \\(\infty\\) (very big).

The two extreme cases for the odds are
- \\( P(Y=1\|\mathbf{X}) \to 1 \\),then the odds gets really big \\(\to \infty\\).
- \\(P(Y=1\|\mathbf{X}) \to 0\\), then the odds goes \\(\to 0\\)

In logit we look at the logarithm of the odds. You will see why soon.

$$ \ln \left( \frac{P(Y=1\|\mathbf{X})}{1-P(Y=1\|\mathbf{X})} \right)$$

By convention we use the natural logarithm because it is nicer to work with mathematically. The log odds ranges from \\((-\infty,\infty)\\).

### Logit model

Here is where the logit *nonlinear probability model* part comes in. It so happens that for many classification problems, the log odds looks like a straight line equation.

$$ \log \frac{P(Y=1|\mathbf{X})}{1-P(Y=1|\mathbf{X})} = \beta \cdot \mathbf{X} = \beta_0 + \beta_1 x_1 + \ldots + \beta_p x_p$$

 This is where it is similar to linear regression! The reason it is still a *nonlinear* model for the probability is that \\(P(Y=1\|\mathbf{X})\\) isn't directly equal to the straight-line-looking part. The log odds is.

 The \\(\beta\\) vector is length \\(p+1\\), where the extra piece is the \\(\beta_0\\) intercept term we tacked on at the beginning. In this case, we can redefine \\(\mathbf{X} = \{ 1, x_1, x_2,\ldots,x_p \} \\) to make the equation look nice. We just tack on a 1 at the beginning for the intercept term and then everything looks nice.

 The \\(\beta\\) vector is a list of numbers that we need to tune to fit our problem. This is what we do when we fit the logit model, just like when we fit a straight line and need to find the best slope and intercept to fit the points.

### Simplified notation

To simplify notation, the left-hand side of the previous equation (the log odds) is often written \\(\mathrm{logit}\, P(Y=1\|\mathbf{X})\\) so that we have

$$ \mathrm{logit}\, P(Y=1\|\mathbf{X}) = \beta\cdot\mathbf{X} $$

Remember that this is a *model*, not an equation dropped from the heavens that governs all classification tasks. We have made certain assumptions here, namely that the log odds is linear in the predictors. That assumption may not hold and should be tested where possible. But since this model is often used in models with large numbers of predictors, deviating from the linear assumption above should only happen when it's really necessary for some reason.


## References

- *Regression models for categorical and limited dependent variables*, J. Scott Long (1997) contains a beautiful description of logistic regression with much of the associated mathematics from two different perspectives. It also discusses the connection between the logit and probit models.
