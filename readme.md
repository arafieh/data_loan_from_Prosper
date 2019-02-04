# Data Loan from Prosper
## by Ali Rafieh


## Dataset Overview

This data set contains 113,937 loans with 81 variables for each loan, including loan amount, borrower rate (or interest rate), current loan status, borrower income, and many others features. Last update for dataset is 03/11/2014 and 43 columns have empty data.

In this investigation I looked forward of common intuition items and features which people thinks have most effect on their loan's amount or rate. So, I tried to figure out the relation between these items in this loan dataset from Prosper. Most exploratory process has done by different graphs. I selected 11 properties (variables) from original dataset and concentrate on them. These variables are: 'Term', 'BorrowerAPR', 'BorrowerRate', 'EmploymentStatus', 'IsBorrowerHomeowner', 'CreditScoreRangeLower', 'CreditScoreRangeUpper', 'InquiriesLast6Months', 'TotalInquiries', 'IncomeRange' and 'LoanOriginalAmount'.

A new column, 'CreditScoreLevels', based on Experian credit score levels, created and input data provided by mean value of 'CreditScoreRangeLower' and 'CreditScoreRangeUpper' for each record.

This new 'CreditScoreLevels' column categorized and ordered in categories from 300 to 850 in 5 ordinal categories base on [Experian](https://www.experian.com/blogs/ask-experian/credit-education/score-basics/what-is-a-good-credit-score/): 'Very Poor',  'Fair', 'Good', 'Very Good', 'Exceptional'.

After cleaning dataset, 8560 records removed and size of final dataset which used was 105377 rows and 10 columns.

### A Short Description of Variables:

Here is a short description of variables which I used in dataset for share terminology:

Variable | Description 
 -------------  | -------------
  Term  | The length of the loan expressed in months. 
  BorrowerAPR  | The Borrower's Annual Percentage Rate (APR) for the loan. 
  BorrowerRate  | The Borrower's interest rate for this loan. 
  EmploymentStatus  | The employment status of the borrower at the time they posted the listing. 
  IsBorrowerHomeowner  | A Borrower will be classified as a homowner if they have a mortgage on their credit profile or provide documentation confirming they are a homeowner. 
  CreditScoreLevels  | The levels of the borrower's credit score as provided by a consumer credit rating agency and assigned based on Experian categories. 
  InquiriesLast6Months  | Number of inquiries in the past six months at the time the credit profile was pulled. 
  TotalInquiries  | Total number of inquiries at the time the credit profile was pulled. 
  IncomeRange  | The income range of the borrower at the time the listing was created. 
  LoanOriginalAmount  | The origination amount of the loan. 

## Summary of Findings

I found, credit score and then income range, are most important items for loan's rate and amount. In dataset, frequency distribution of loan's rate and APR, mainly covered each other with a little step ahead for loan's APR. 

Both inquiries variables in dataset, don't have meaningful relation with loan's rate and amount, but they were completely effective on credit score. Credit score has inverse relation with both inquiries, but sensitivity of credit score to inquiries after 'Very Poor' score, sharply fade and in 'Good', 'Very Good' and 'Exceptional' scores, has little change vs. number of inquiries on both, total and last 6 months. In other words, maybe say credit score after 'Good' or 'Very Good' other features become more important for changing levels of credit score.

I found loan's 'Term' does not take effect of borrower situations and more relying on loan's rate and amount, also rate has inverse relation to amount.

I expected in all levels of ‘Credit Score Levels', borrowers with 'Not employed' value in 'Income Range' have higher loan's rate and lower loan's amount, this trend has been followed by different credit score levels but 'Very Poor' and 'Exceptional'.
In 'Very Poor level, interestingly, 'Not employed' borrowers got higher loan's amount than 2 lower income categories and average loan's amount for them is equal to $ 50k-75k. This category got lower loan's rate rather than of the rest income categories in this level.
For 'Exceptional' level, challenging founding limited to loan's amount and loan's rate follow our expectation. They took higher amount than $ 1-25k, equal to borrowers with $ 25k-50k income range. Rest of graph comply our intuition expectation: higher 'Income Range' in all 'Credit Score Levels' could take higher loan's amount with lower loan's rate.


## Key Insights for Presentation

In presentation I mainly concentrate on plots and graph related 2 variables, loan's rate and loan' amount and relation of other variables with them. Based on this idea, I first bring some graphs and plots witch show a picture of dataset situation, plots like frequency distributions of loan’s amount in a logarithmic scale, credit score, borrowers home owner situations, income range, employment status and loan's term. Then used bivariate barplot to demonstrate credit score, as a categorical variable, in front of numeric variables like loan’s amount and rate, and both inquiries variables.

As following main idea, after showing credit score situation vs. all numeric variables, I show effect of the rest categorical variables (employment status, homeowner and income range) on loan's rate and amount by boxplot, as well regplot was really great to show how different levels of credit score distribute by loan' rate and loan's amount.

At the end I used pointplot to show how my expectation about how borrowers with higher income range, get higher loan's amount and lower loan's rate, got face challenge by 'Very Poor' credit score.
