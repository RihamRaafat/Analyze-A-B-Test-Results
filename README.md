# Analyze-A-B-Test-Results
For this project, you will be working to understand the results of an A/B test run by an e-commerce website. Your goal is to work through this notebook to help the company understand if they should implement the new page, keep the old page, or perhaps run the experiment longer to make their decision.

Conclusions¶
To start analyzing the attached results from A/B test for a company, we took a look at our data and prepare it to analysis by dropping the duplicated rows, repeated users id, and also mismatching results (control group with new page & treatment group with old page). Now we have the data in good format, we will analyze it in many different ways:
1- Statistical Probabilities:

Conversion rate: 12% Old page conversion rate: 12.04% with 49.99% showing rate. New page conversion rate: 11.88% with 50.01% showing rate. That may suggest that the old page is better but the difference range is really small and don't reflect any directions.

2- Hypothesis Testing:

Here we will perform hypothesis test in a Type I error of (5%) which means \alpha = 0.05, we assumed that the old page is better till we have an evidence that the new one has higher conversion rate and that could be represented as following: 𝐻0:𝑝𝑛𝑒𝑤−𝑝𝑜𝑙𝑑≤0 𝐻1:𝑝𝑛𝑒𝑤−𝑝𝑜𝑙𝑑>0

We simulated the difference between conversion rate of new page and old page of 10,000 sample and got a very small difference could tend to zero, then we calculated the P value which will help us to take a decision and it was significantly large which leads us to build an initial opinion to stay with the null (old page). We used another technique to calculate the P value and reach same result.

3- Regression:

Since we need to predict whether an individual will be converted or not, we will use the logistic regression, we prepared our dataframe and fitted the model and got the summary which agreed also with our hypothesis testing results and we can note a slightly effect of the page to the conversion rate (-0.015) the coff associated with ab_page.

New data has been invited to our model (country) we have three countries (US, UK, CA), we repeated the last process of creating dummies (using only 2 in case of 3) and got the summary of the fitted model which concluded that all the factors have very little impact on the results, we may say that if the user from US, that would be more likely to turn converted than UK & CA.

Finally we can suggest the following:

Continue in the treatment for a longer time.
Stay with the old page.
Get more detailed data about users and treatment like (age, time spent).
Show the new page more to new users, old users data could be biased.
