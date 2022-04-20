# Introduction and Business Case

This project involves an A/B test to find out which ad to show to customers to increase Response Rates for a business.

The purpose of the ad is to encourage the customer to fill out a 'BIO questionnaire'. Response Rate is defined as the sum of observations/customers where the customer interacts with the questionnaire (choosing either 'Yes or 'No', as opposed to choosing neither 'Yes' or 'No') divided by the sum of observations.

The business would like to see a 2% increase in response rate between a dummy ad (control group) and a Smart Ad (exposed or treatment group), also known as a Creative Ad

## Null and Alternative hypothesis

We hypothesise that our 'exposed' group will have a higher response rate compared to our 'control' group. So this will be a one-tailed test.

If **p<sub>c</sub>** = response rate of the control group and **p<sub>e</sub>** = response rate of the exposed group, then:

H0: SmartAd recipients that receive the Creative Ad will have the *same response rate* as the response rate of recipients who receive the dummy ad

**p<sub>c</sub>** = **p<sub>e</sub>**


H1: SmartAd recipients that receive the Creative Ad will have *a higher response rate* than the response rate of recipients  who receive the dummy ad

**p<sub>c</sub>** < **p<sub>e</sub>**

# Data

## Data Source:

The data is obtained from [Kaggle](https://www.kaggle.com/datasets/osuolaleemmanuel/ad-ab-testing) and was uploaded by user [Osuolale Emmanuel](https://www.kaggle.com/osuolaleemmanuel)

## Columns:

- auction_id	the unique id of the online user who has been presented the BIO. In standard terminologies this is called an impression id. The user may see the BIO questionnaire but choose not to respond. In that case both the yes and no columns are zero
- experiment	which group the user belongs to - control or exposed.
- date	the date in YYYY-MM-DD format
- hour	the hour of the day in HH format.
- device_make	the name of the type of device the user has e.g. Samsung
- platform_os	the id of the OS the user has.
- browser	the name of the browser the user uses to see the BIO questionnaire.
-    yes	1 if the user chooses the “Yes” radio button for the BIO questionnaire.
-    no	1 if the user chooses the “No” radio button for the BIO questionnaire.


## Sample sizes

There are 4000+ observations for both the control and exposed groups

# EDA

EDA was kept limited and covers the following:

- Number of Observations in Each Sample
- Response Rates of Both groups
- Number of responses by hour of day
- Total number of individuals who received an ad - by hour of day
- Response rates by Date and Group


# Hypothesis Test

## Which test to use

A Z-test was used, owing to the fact that we are working with proportions (respose rate) and large number of observations

# Test and Business Conclusions

The test resulted in a p-value of **0.0124**, which is less than 0.05.Therefore, we may reject the null hypothesis. It is highly likely that the response rate of the exposed group which sees the creative ad is greater than the response rate of the control group which sees the dummy ad.

The confidence intervals tell us a similar story. The CI for the exposed group i) does not include the control group response rate of 0.143945 and ii) does include the 2% increase the business aimed to see (0.143945 + 0.02 = 0.163945)

This means that the business can be highly confident that the Creative Ad elicits more response rates from its customers, and that it should from now on show the Creative Ad to all of its customers (the population)
