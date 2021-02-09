# Analyze A/B Test Results

This project will assure you have mastered the subjects covered in the statistics lessons. The hope is to have this project be as comprehensive of these topics as possible.
Important to notice that codes passes the project [RUBRIC](https://review.udacity.com/#!/rubrics/1214/view). 

Table of Contents
Introduction
Part I - Probability
Part II - A/B Test
Part III - Regression

# Introduction
A/B tests are very commonly performed by data analysts and data scientists. It is important that you get some practice working with the difficulties of these

For this project, you will be working to understand the results of an A/B test run by an e-commerce website. Your goal is to work through this notebook to help the company understand if they should implement the new page, keep the old page, or perhaps run the experiment longer to make their decision.

As you work through this notebook, follow along in the classroom and answer the corresponding quiz questions associated with each question. The labels for each classroom concept are provided for each question. This will assure you are on the right track as you work through the project, and you can feel more confident in your final submission meeting the criteria. As a final check, assure you meet all the criteria on the [RUBRIC](https://review.udacity.com/#!/rubrics/1214/view). 

# Software needed are:
import pandas as pd
import numpy as np
import random
import matplotlib.pyplot as plt
%matplotlib inline

_We are setting the seed to assure you get the same answers on quizzes as we set up_
random.seed(42)


# Part I - Probability
To get started, let's import our libraries.
The above code had cleaned the non matching rows including the control group ones
**My question is: how did this code clean up the unmatching rows while we did not include the control and/or old_page ?**

# Part II - A/B Test
Notice that because of the time stamp associated with each event, you could technically run a hypothesis test continuously as each observation was observed.

However, then the hard question is do you stop as soon as one page is considered significantly better than another or does it need to happen consistently for a certain amount of time? How long do you run to render a decision that neither page is better than another?

These questions are the difficult parts associated with A/B tests in general.

  1. For now, consider you need to make the decision just based on all the data provided. If you want to assume that the old page is better unless the new page proves to be definitely better at a Type I error rate of 5%, what should your null and alternative hypotheses be? You can state your hypothesis in terms of words or in terms of  𝑝𝑜𝑙𝑑  and  𝑝𝑛𝑒𝑤 , which are the converted rates for the old and new pages.

# Our null and alternative:
𝐻0:𝑝𝑛𝑒𝑤−𝑝𝑜𝑙𝑑≤0
 
𝐻1:𝑝𝑛𝑒𝑤−𝑝𝑜𝑙𝑑>0


# Part III - A regression approach
  1. In this final part, you will see that the result you achieved in the A/B test in Part II above can also be achieved by performing regression.

    a. Since each row is either a conversion or no conversion, what type of regression should you be performing in this case?

## This is Logostic Regression.

  b. The goal is to use statsmodels to fit the regression model you specified in part a. to see if there is a significant difference in conversion based on which page a customer receives. However, you first need to create in df2 a column for the intercept, and create a dummy variable column for which page each user received. Add an intercept column, as well as an ab_page column, which is 1 when an individual receives the treatment and 0 if control.
  
  
# Important Notes:
First look at the data, indicates that the old page is better than the new page, as the conversion rate of control group is higher by 8% points.
However, we need to consdier three main factors in our analysis.
  1 - The controle group might be bias in the result due to unfair advantage to the old version - the Change Avergion theory.

  2 - We might also fall inot the Simpson's Paradox.

  3 - Need to understand the timeframe of the abalysis done, was it enough to generate such a cnclusion, also important to check the total number of participants and if it is an enough sample size to influence teh decision.

That is why we must statistically observe the engagement within each of the groups, and this would require us to measure:
The confidence intervals using the central limit theorem. The standard deviation and the sampling distribution of the mean using the A/B hypothesis tests.  

