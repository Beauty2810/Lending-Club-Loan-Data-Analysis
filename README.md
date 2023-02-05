# Lending-Club-Loan-Data-Analysis
# Description:
LendingClub is a US peer-to-peer lending company, headquartered in San Francisco, California.[3] It was the first peer-to-peer lender to register its offerings as securities with the Securities and Exchange Commission (SEC), and to offer loan trading on a secondary market. LendingClub is the world's largest peer-to-peer lending platform.

# Our Goal
Given historical data on loans given out with information on whether or not the borrower defaulted (charge-off), can we build a model that can predict wether or nor a borrower will pay back their loan? This way in the future when we get a new potential customer we can assess whether or not they are likely to pay back the loan. The "loan_status" column contains our label.

# Data
This dataset contains the full Lending Club data available from their site. The data used contain all the Loans of the Lending Club during the period 2007 - 2018 consisting of > ~1.5M samples and > 150 features.

# EDA
Exploratory Data Analysis, or EDA, is an integral part of understanding the LendingClub dataset.
## Loan Status Distribution

<img width="553" alt="image" src="https://user-images.githubusercontent.com/108981162/216836458-73c8c074-d980-4334-8c87-dc51eb74623f.png">

We will be considering only two categories, "Fully Paid" and "Charged Off". It is clearly visible that the data is imbalanced and we have to take the actions accordingly.

<img width="392" alt="image" src="https://user-images.githubusercontent.com/108981162/216836617-d6450fbc-6047-4f1b-ac15-6bb14b9d4dfb.png">

This plot identifies the distributions of loan interest rate records within the dataset.

<img width="494" alt="image" src="https://user-images.githubusercontent.com/108981162/216837018-d15dad46-6efb-450d-bb41-0de04e29dfee.png">

Here is a simple count plot for loan grades within the dataset. The most popular grades are B and C. A-graded loans come third. There are few F and G graded loans, probably for the best. However it is important to notice that B and C graded loans occur more often than top rated 'A' loans.

## Data Preprocessing

- Discarding all the columns containing more than 25% null values of the total data
- Imputing null values with suitable feature values
- Converting all date features into datetime datatype and creating separate features containing month and year of that date feature
- Reducing number of feature based on feature importance obtained from Random Forest Classifier
- Converting categorical features to numerical features using label encoding
- Scaling the features for fast convergence of the model
- Spliting the data into training and testing 

## About Model 

We trained a 4-layer Neural Network using Keras having total Trainable params: 23,271. Since, the data was imbalanced, f1_score, precison and recall were taken into consideration for the evaluation of the model. We managed to get f1_score of 99% for the test data.
