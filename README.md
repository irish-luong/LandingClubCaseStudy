# Project Name
> Apply EDA to analyze a financial case study - Lending Club Case Study
 

## Table of Contents
- [Project Name](#project-name)
  - [Table of Contents](#table-of-contents)
  - [General Information](#general-information)
    - [Context](#context)
    - [Business Objectives](#business-objectives)
    - [Interpreted The Meaning of Dataset](#interpreted-the-meaning-of-dataset)
  - [Conclusions](#conclusions)
  - [Technologies Used](#technologies-used)
  - [Acknowledgements](#acknowledgements)
  - [Contact](#contact)

## General Information 

### Context

When a person applies for a loan, there are two types of decisions that could be taken by the company:

- Loan accepted: If the company approves the loan, there are 3 possible scenarios described below:

    -  Fully paid: Applicant has fully paid the loan (the principal and the interest rate)

    - Current: Applicant is in the process of paying the instalments, i.e. the tenure of the loan is not yet completed. These candidates are not labelled as 'defaulted'.

    - Charged-off: Applicant has not paid the instalments in due time for a long period of time, i.e. he/she has defaulted on the loan 

- Loan rejected: The company had rejected the loan (because the candidate does not meet their requirements etc.). Since the loan was rejected, there is no transactional history of those applicants with the company and so this data is not available with the company (and thus in this dataset)
![loan_image](./img/Loan_image.png)

### Business Objectives

The company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default.  The company can utilise this knowledge for its portfolio and risk assessment. 

### Interpreted The Meaning of Dataset

![data_overview](./img/data_overview.png)

- Dataset contains the complete loan data for all loans issued through the time period 2007 t0 2011 (given in module introduction).
- There are 39717 rows and 111 columns
- There are 54 columns with highest missing values 39717. I think we should remove these after looking into it carefully. Some of them might be ouput columns where we need to find the values.
- Also few columns are there with many missing values. Some columns contain 1k, 2.4k, 12.9k, 25k, 37k, 38k missing values in it.


## Conclusions
- <span style="color:green">Inferences - Unordered Univariate Analysis :  </span>
  - Term = Most of the loans (73%) have 36 months tenure where as only 26% loans have 60 months tenure.
  - Grade = Most common loan grades are B(30%), A(25%) and C(20%)  
  - home_ownership, purpose = Most of the borrowers dont have their own house. 92% borrowers either pay "Rent" or "Mortgage" their house. But only 1% borrowers''purpose' of the loan is 'house'. And 47% borrowers' purpose is 'debt_consolidation'.  
  - verification_status = 42% of the borrowers' income is 'not verified' which is risky.  
  - loan_status = Only 14% of the borrowers are 'Defaulters'   

- <span style="color:green">Inferences - Univarite or Bivariate Analysis on Categorical Variables: </span>
  - Term - Loans with 60 months tenure have double chances (22.6%) of getting default than loans with 36 months tenure (11.1%)
    
  - Grade - G grade loans have highest chance of getting default (32%). Where as A grade loans have less chances of getting default(only 6%).
    
  - emp_length - There is a 15% chance of loan getting default when employment length of the borrower is 10+ years.  
    
  - Home_ownership - Most of the loan borrowers dont have their own house. Their home is either Rented or Mortgaged. There is almost 13 to 15 % chance of these borrowers getting defaulted.   

  - Verification Status - For Non - Verified Loan, 12% chance is there for getting defaulted.

  - Purpose - Loans with small business purpose have highest chances (26%) of getting defaulted. Whereas loans for wedding, car or major purchase have lowest chances (only 10%) of getting defaulted.

  - Address State - NE state has very high loan defaulting status (60%).

  - inq_last_6months - Higher number of inquiries is indication of high chances of defaulted loan.  

- <span style="color:green">Inferences - Ordered Univariate Analysis: </span>
  - emp_length = Most of the borrowers (22.4%) have  10+ years of employment length. 
  - inq_last_6mths = Half of the times (48%) there is no inquiry or 0 inqury in last 6 months

- <span style="color:green">Inferences - Segmented Univarite Analysis:  </span>
  - Loan_amount and Term : Loan amount is higher for 60 months tenure loans than that of 36 months tenure loans  
  - Loan_amount and Grade : Loan amount is higher for the loans with grades G, F, E ampared to other grade loans  
  - Loan_ amount and Varification status : Loan amount is higher for the Verified loan status than Not verified loan status   
  - Int_rate and Term : Interest rate is high for 60 months tenure loans than 36 months tenure loans  
  - Int_rate and Grade : Interest rates gradually increase for the loans with grades A, B, C, D, E, F, G. G grade loans have highest interest rates where as A grade loans have lowest interest rates.  
  - total_rec_prncp and Term : Principal received till date is high for the 60 month tenure loans than 36 months loans  
  - total_rec_prncp and Grades: Principal received till date is high for the G grade loans than any other grade loans  
  - total_rec_prncp and is default : For defaulted loans, principal received till date is very less.  
  - revol_util and grade: Revolving line utilization rate (the amount of credit the borrower is using relative to all available revolving credit) is lowest for grade A loans and it is highest for grade G loans  
  - revol_util and is_default : Revolving line utilization rate is high for defaulters than non-defaulters.  

- <span style="color:green"> From Segmented Univariate Analysis on Default status </span>
  - int_rate - Default loan has higher interest rate than non-default loans. On an average default loan interest rate is 13.88% (2% higher) where as for non default loan interest rate is 11.7%.   

  - We can say that defaulter borrowers' annual income is less compared to non-defaulter borrowers'.  

  - total_rec_prncp - We can clearly see that there is a hugh difference in principal received from defaulters and non-defaulters. Average principal received from non defaulters is around 10.7K where as from non- defaluters is only 4k. Which is almost 60% less principal received from defaulters compared to non-defaulters.   

  - revol_util - Revolving line utilization rate is higher for the defaulters than non-defaulters. Loan given to higher amount of credit  borrower is using relative to all available revolving credit leads to loan default.
     
  - open_acc - Number of open credit lines in defaulters credit file is less compared to non-defaulters. 
  
- <span style="color:green">Inferences - Segmented Univariate Analysis on Default status on timeseries:  </span>
  - Number of loan applicants are increasing over the period of time.
  - Total borrowers in 2011 is highest i.e. 21K
  - On an average loan amount given to the borrowers is high in 2nf half of the year compared to first half

- <span style="color:green">Inferences - Bivariate Analysis on Continuous Variables:  </span>
  - loan_amnt, funded_amnt, funded_amnt_inv = We can say there is a very high correlation between loan amount applied by the borrower and loan amount committed by the investor to the borrower. So whenever loan application of the borrower gets passed by company, then he gets almost full amount of the loan applied.
    
  - loan_amnt, installment, total_rec_prncp - It is also obvious that monthly installment and loan amount are highly correlated. Higher the loan amount, higher is monthly installment and and higher is principal received  vice versa.
    
  - total_acc, open_acc- Number open credit lines is also highly correlated with total number of credit lined in the borrower's credit file.  

  - revol_util, int_rate - Revolving line utilization rate and interest rate are moderately correlated with each other. Higher the amount of credit the borrower is using, higher is the risk of loan repayment. Thats why higher is the interest rate, and vice-versa.

- <span style="color:green">Inferences - Correlation Between Loan Amount, Funded Amount, Installment:</span>  
  - Funded amount by the company is always less than or equal to loan amount applied by borrower.  
  - Funded amount by the company is highly correlated with monthly installment paid by the borrower.  
  - There is a high correltion between loan amount, funded amount and installment

- <span style="color:green">Inferences - Bivariate Analysis on Categorical Variables:  </span>

  - term & Grade - G grade loans with 36 month tenure has highest chance of default (37%) where as A grade loans with 36 month tenure has lowest chance of default(5.9%).  

  - term & Pupose - Education loan and small business purpose loan with 60 month tenure is very likey to get default (43.8% and 35% resp).  

  - Grade and emp_length - G grade loans with 1 year of employment length has very high chance of getting defalt i.e. 70.6%. F grade loans with 9 years of employment length has second highest chance of getting defalt i.e. 47.6%.  

## Technologies Used
- ydata_profiling - version 23.2.1
- ipywidgets - version 8.1.1
- termcolor - version 2.3.0

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
- This project was inspired by [seaborn](https://seaborn.pydata.org/index.html).


## Contact
Created by [Dnyaneshwari Chidrawar](https://github.com/Dnyaneshwari-Chidrawar) and [Duc-Luong](https://github.com/irish-luong) - feel free to contact us!
