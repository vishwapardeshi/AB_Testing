# A/B Testing 

A/B Testing is a user experience methodology. It is essentially an experiment where two or more variants of a page are shown to users at random, and statistical analysis is used to determine which variation performs better for a given conversion goal. It involves splitting the user group into two - A(Control) and B(Variant) Groups.

The experimental design of A/B test will be explored along with two types of experiments
1. Randomized Design
2. Matched-Pair Design

## Outline

This repositories contain experiments which were designed to gain a better understanding of A/B testing and analyzing results. This repository additional contains notebooks which explore early stopping, power analysis, experiment duration. 

Tools used 
1. Alteryx
2. Python
3. Jupyter Notebooks

## When to use A/B Testing?
A/B Testing can be used to solve business problems when you don't have enough data to use modeling techniques.

#### Business Scenario - New Product Introduction

Consider that you are working as a product manager of a toy manufacturing company. A new product is ready for distribution but the company is unsure of its success. 

In this scenario, A/B testing can be used to predict the effect on sales if the new toy is introduced. This will help the management determine if it should go into full distribution. A/B test is a natural choice as we have first a binary situation and second no past information to build models. 

## Terminologies
In A/B test, we design experiments. 

**1. Unit** - In an experiment in a test, each individual is called an unit. In our case, it is a shop. 

**2. Treatment Group** - Collection of units getting the treatment. Treatment is the change we are testing. Treatment group is the one where the new product will be sold.

**3. Control Group** - Baseline comparison for the treatment group. The control group is the one where the new product will not be sold. 

**4. Target Variable** - The variable for which we are trying to predict the outcome for. In our case, the target variable is the sales.

**5. Experimental Variables** - It is also known as the treatment/independent variables. This is the variable we change to see how it impacts the target variable. In our case, the experimental variable is the sale of the new toy.

**6. Control Variables** - The data we have about the units are called control variables. They are the variables which are most influential wrt target variables. In our case, the additional information which we can have about the store are customer demographics, location and sales are our control variables. *Different than predictor variable as they are used to ensure that the treatment and control units are as similar to each other as possible.* This is important as we want to measure the impact of the product launch independent of other factors.


## 5 steps to identify Control Variables
1. List potential variables 

Business Scenairo - Number of products offered, Total volume of category sold, size & location of store, customer demographics, number of customers, number of competitve products.

2. Is variable data available - Do you have data for these variables?

Business Scenairo - Number of products offered, Total volume of category sold, size & location of store, customer demographics

3. Ensure that there exists logical connection between control & target variables

Business Scenairo - Location & demographics are likely measuring the same thing and hence can be eliminate one of two

4. Test correlation between control & target variables

Business Scenairo - Test correlation using Alteryx - association aanlysis, plot of means were used to determine that number of products offered and state is correlated with target variable.

5. Test correlation between control variables to avoid similar variables

Business Scenairo - No such variables were found. 

## Experiment Duration
This depends on the objective of the data. A general rule is to run the experiment for a full cycle of data. It means to run the experiment for a duration that will allow you to gather data which is representative of the population. 

If this is not followed then there is a higher chance of bias in the responses. However, full cycle length can't be determined accurately, thus it is upto us to baalnce business constraints and accuracy.

## Experimental Design

### Randomized Design 
This design involves sampling the control and treatment group completely randomly.

##### When to use?
It is used in situation where it is very difficult to control variables. The volume & velocity of the data is high enough that we are not worried about bias. Thus, it is used when:

1. High Volume of Observations

2. Low concern for Bias

3. Low cost per observations

Example - Website based & telephone based experiments as they have little control over who visits/calls.

### Matched-Pair
This design involves sampling the control and treatment group completely randomly.

##### When to use?
It is used in situation where there is low traffic. Running this test can be very expensive so we should try to reduce the number of treatment units to a minimum. A matched pair experiment can yield significant results even with a low number of treatment units. Thus, it is used when:

1. Low Volume of Observations

2. High concern for Bias

3. High cost per observations

Example - Website based & telephone based experiments the treatment & control units are matched on a unit-to-unit basis using a wieghting of identifying control variables. This eliminates sources of bias & increase confidence.

##### How to setup Matched Pair?
1. Must be set up ahead of time

2. All units must be known before the start of the experiments.







