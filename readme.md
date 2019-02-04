
# Data Loan from Prosper
## by Ali Rafieh


## Dataset

This data set contains 113,937 loans with 81 variables on each loan, including loan amount, borrower rate (or interest rate), current loan status, borrower income, and many others features, with last update 03/11/2014 and 43 columns have empty data.
The size of dataset is 113937x81 and most columns are numeric. 43 columns have empty data. 

In this investigation I looked forward of common intuition items and features which people thinks have most effect on their loan's amount or rate. So, I tried to figure out the relation between these items in loan data from Prosper. Most exploratory process has done by different graphs. I selected 11 properties (variables) from original dataset and concentrate on them. These variables are: 'Term', 'BorrowerAPR', 'BorrowerRate', 'EmploymentStatus', 'IsBorrowerHomeowner', 'CreditScoreRangeLower', 'CreditScoreRangeUpper', 'InquiriesLast6Months', 'TotalInquiries', 'IncomeRange' and 'LoanOriginalAmount'.

A new column, 'CreditScoreLevels', based on Experian credit score levels, created and input data provided by mean value of 'CreditScoreRangeLower' and 'CreditScoreRangeUpper' for each record.

This new CreditScore column need to categorized and ordered in categories from 300 to 850 in 5 ordinal categories base on [Experian](https://www.experian.com/blogs/ask-experian/credit-education/score-basics/what-is-a-good-credit-score/): 'Very Poor',  'Fair', 'Good', 'Very Good', 'Exceptional'.
After cleaning dataset, 8560 records removed.

### A Short Description of Variables:

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

Both inquiries variables in dataset, don't have meaningful relation with loan's rate and amount, but they were completely effective on credit score. Credit score has inverse relation with both inquiries, but sensitivity of credit score to inquiries after 'Very Poor' score, sharply fade and in 'Good', 'Very Good' and 'Exceptional' scores, has little change vs. number of inquiries on both, total and last 6 months. In other words, maybe say credit score after 'Good' or 'Very Good' lose its sensitivity to inquiries and other features become more important for changing credit score levels.

I found loan's 'Term' take effect of borrower situations and more relying on loan's rate and amount, also rate has inverse relation to amount.

I expected in all levels of ‘Credit Score Levels', borrowers with 'Not employed' value in 'Income Range' have higher loan's rate and lower loan's amount. As following plots show, this trend has been followed by different credit score levels but 'Very Poor'. In this level, interestingly, 'Not employed' borrowers got higher loan's amount with lower loan's rate rather than of the rest levels. Beside this note, rest of graph comply our intuition expectation: higher 'Income Range' in all 'Credit Score Levels' could take higher loan's amount with lower loan's rate.

## Key Insights for Presentation

For presentation, I first brings some graphs and plots witch show inside situation of dataset, like frequency distributions of loan’s amount in a logarithmic scale, credit score, borrowers home owner situations, income range, employment status and loan's term. Then used bivariate barplot to demonstrate credit score, as a categorical variable, in front of numeric variables like loan’s amount and rate, and both inquiries variables.

In presentation I mainly concentrate on 2 variables, loan's rate and loan' amount. So, after showing credit score situation vs. all numeric variables, I shows effect of the rest categorical variables (employment status, homeowner and income range) on loan's rate and amount by boxplot, although regplot was really great to show how different levels of credit score distribute by loan' rate and loan's amount.

At the end I used pointplot to show how my expectation about how borrowers with higher income range, get higher loan's amount and lower loan's rate, got face challenge by 'Very Poor' credit score.
