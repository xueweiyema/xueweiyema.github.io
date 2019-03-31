# <center>  Customer Segmentation Report for Arvato Financial Services </center>
*A report for Udacity Data Scientist Capstone Project*


## Introduction

In this project, I would analyze demographics data for customers of a mail-order sales company in Germany, comparing it against demographics information for the general population. I'll use unsupervised learning techniques to perform customer segmentation, identifying the parts of the population that best describe the core customer base of the company. Then, I'll demographics information for targets of a marketing campaign for the company, and use a model to predict which individuals are most likely to convert into becoming customers for the company. The data of the project that has been provided by our partners at Bertelsmann Arvato Analytics, and represents a real-life data science task.

## Get to Know the Data
There are 4 data set in this project.<br>
AZDIAS: Demographics data for the general population of Germany; 891 211 persons (rows) x 366 features (columns).<br>
CUSTOMERS: Demographics data for customers of a mail-order company; 191 652 persons (rows) x 369 features (columns).<br>
MAILOUT_TRAIN.csv: Demographics data for individuals who were targets of a marketing campaign; 42 982 persons (rows) x 367 (columns).<br>
MAILOUT_TEST.csv: Demographics data for individuals who were targets of a marketing campaign; 42 833 persons (rows) x 366 (columns).<br>
Each row of the demographics files represents a single person, but also includes information outside of individuals, including information about their household, building, and neighborhood. <br>
I will deal with the AZDIAS dataset and the CUSTOMERS dataset and use unsupervised learning to perform customer segmentation,The result would be described parts of the general population that are more likely to be part of the mail-order company's main customer base.

I will show the overall data situation.AZDIAS dataset contains 366 features and CUSTOMERS dataset contains more 3 feature about customer infomation than AZDIAS dataset.
![avatar](/pic/azdias_customers_head.jpg)
Randomly present the distribution of several dimensions
KBA13_ANTG3
![avatar](/pic/KBA13_ANTG3.jpg)
KBA13_BJ_2004
![avatar](/pic/KBA13_BJ_2004.jpg)
D19_BUCH_HD
![avatar](/pic/D19_BUCH_HD.jpg)
KBA13_HALTER_45
![avatar](/pic/KBA13_HALTER_45.jpg)

It can be seen from the distribution diagram of the above features that they are normally distributed.

## Clean the Data
I will process the data in five steps

### a) Deal with the missing data features and row
This project provides two documentation.There are 'DIAS Attributes - Values 2017.xlsx' and 'DIAS Information Levels - Attributes 2017.xlsx'.
In these documentation there are some descriptions about the unknown value.

![avatar](/pic/unknown.jpg)

I think the unknown value can be replaced with a nan value.Let us check the distribution of nan values

![avatar](/pic/missing_value_of_col.jpg)

I would remove the features that has over 30% missing rate. 

![avatar](/pic/missing_value_of_row.jpg)

I would remove the row that has over 10% missing rate

### b) Deal with the numerical features

I found the numerical features based on the attribute type and the total number of each attribute value.

features group by datatype 
![avatar](/pic/dtype.jpg)

total number of each attribute value
![avatar](/pic/value_counts.jpg)

The numerical feature might have more value,so I will check the value count bigger than 30.I will use the mean to fill in the nan value for the numerical features.

### c) Deal with the categories features

