# Fraud detection

## Purpose
This hands-on exercise is meant to:
- Ensure your skills align with your potential role at AlphaSights. 
- Let you exhibit your skills in a simulated data science problem
- In the case of a successful take home exercise, shorten the time commitment for the final round of interviews 
- Provide some common ground for follow-up discussions in the final round
- Hopefully provide a fun experience working with a new data set!

## General Guidance
- You should expect to spend roughly 3 hours on this exercise. You should be able to load the data, perform some exploratory analysis, do some feature engineering, and finally select and train a model. 
- Given the limited time frame, the expectation is that you spend more time understanding and exploring the data and limited time on model training and tuning. We do not expect you to deliver a highly accurate model in the given time. 
- We are particularly interested in what features you choose to include in the model. 
- Feel free to pick the model type you are most familiar with, provided that you can defend the assumption that it is appropriate and could lead to "good" predictions. 

## Final Deliverable
You may use whatever language/ packages/ libraries you wish. We find the most convenient final product is a Jupyter notebook, though we will accept Excel, R, even Cobol if that's your thing!

To aid with our understanding of what you have done, where possible please include brief comments explaining the work you have done. A brief one paragraph summary can also be helpful (high level approach taken, interesting findings in the data, etc). 

## The Problem
The goal is to predict the probability that an online transaction is fraudulent, as denoted by the binary target isFraud. After thinking through the problem, you can define what a "good" model means.

## The Data Set
The data for training your model is available here. It is broken into two files, identity.csv and transaction.csv, which are joined by TransactionID. Not all transactions have corresponding identity information.

Note: Further details on the two tables are included below. To make this exercise more manageable in the given time frame, a number of columns have been eliminated, so the description below is a superset of actual fields available.

### Transaction Table

| Field | Description |
| ----- | ----------- |
| TransactionDT | timedelta from a given reference datetime (not an actual timestamp) |
|TransactionAMT| transaction payment amount in USD|
|ProductCD| product code, the product for each transaction|
|card1 - card| payment card information, such as card type, card category, issue bank, country, etc.|
|addr| address|
|dist| distance|
|P_ and (R__) emaildomain| purchaser and recipient email domain|
|C1-C14| counting, such as how many addresses are found to be associated with the payment card, etc. The actual meaning is masked.|
|D1-D15| timedelta, such as days between previous transaction, etc.|
|M1-M9| match, such as names on card and address, etc.|
|Vxxx| Vesta engineered rich features, including ranking, counting, and other entity relations.|

Transaction Table Categorical Features:

| Field | Description |
| ----- | ----------- |
|ProductCD||
|card1 - card6||
|addr1, addr2||
|P_emaildomain||
|R_emaildomain||
|M1 - M9||

### Identity Table 
Variables in this table are identity information – network connection information (IP, ISP, Proxy, etc) and digital signature (UA/browser/os/version, etc) associated with transactions.
They're collected by Vesta’s fraud protection system and digital security partners.
(The field names are masked and pairwise dictionary will not be provided for privacy protection and contract agreement)

Categorical Features:

| Field | Description |
| ----- | ----------- |
|DeviceType||
|DeviceInfo||
|id_12 - id_38||

