# <center>  Customer Segmentation Report for Arvato Financial Services </center>
*A report for Udacity Data Scientist Capstone Project* <br>
![avatar](/pic/1.jpg)

## Introduction

In this project, I would analyze demographics data for customers of a mail-order sales company in Germany, comparing it against demographics information for the general population. I would use unsupervised learning techniques to perform customer segmentation, identifying the parts of the population that best describe the core customer base of the company. Then, I would demographics information for targets of a marketing campaign for the company, and use a model to predict which individuals are most likely to convert into becoming customers for the company. The data of the project that has been provided by our partners at Bertelsmann Arvato Analytics, and represents a real-life data science task.

## Get to Know the Data
There are 4 data set in this project.<br>
AZDIAS: Demographics data for the general population of Germany; 891 211 persons (rows) x 366 features (columns).<br>
CUSTOMERS: Demographics data for customers of a mail-order company; 191 652 persons (rows) x 369 features (columns).<br>
MAILOUT_TRAIN.csv: Demographics data for individuals who were targets of a marketing campaign; 42 982 persons (rows) x 367 (columns).<br>
MAILOUT_TEST.csv: Demographics data for individuals who were targets of a marketing campaign; 42 833 persons (rows) x 366 (columns).<br>
Each row of the demographics files represents a single person, but also includes information outside of individuals, including information about their household, building, and neighborhood. <br>
I would deal with the AZDIAS dataset and the CUSTOMERS dataset and use unsupervised learning to perform customer segmentation,The result would be described parts of the general population that are more likely to be part of the mail-order company's main customer base.

I would show the overall data situation.AZDIAS dataset contains 366 features and CUSTOMERS dataset contains more 3 feature about customer infomation than AZDIAS dataset.
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

It could be seen from the distribution diagram of the above features that they are normally distributed.

## Clean the Data
I would process the data in three steps

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

The numerical feature might have more value,so I would check the value count bigger than 30.I would use the mean to fill in the nan value for the numerical features.

### c) Deal with the categories features

I replace some singular value in categories and redefine the datatype with float.

For example: The feature 'CAMEO_DEUG_2015'
![avatar](/pic/cameo.jpg)

## Customer Segmentation 
I would normalize the data with StandardScaler and reduce the dimension with PCA.

![avatar](/pic/reduce_features.jpg)

![avatar](/pic/features_ratio.jpg)

I have done dimensionality reduction by getting explained ratio of principal components, As i observed 120 components/ eigen values were sufficient to explain more 80% variance in data so I opted that out.

At last I cluster the data with the KMeans.

![avatar](/pic/kmeans.jpg)

I think 17 is the best from the above picture based on the average distance.I would show the 17 number of clusters for the segmentation task.

![avatar](/pic/result.jpg)

I computed the percentage of all 17 clusters of the two datasets which were the demographics data and the customers data.
I drawed the percentage of the clusters pictures for each data.
I found the overrepresented cluster 8 and the underrepresented cluster 14.
The cluster 8 contained component 0 which was the top1 components
The cluster 14 contained component 0 and component 2 which were the top2 components
The component 0 contained KBA13_ANTG3,PLZ8_ANTG3,KBA13_BAUMAX,KBA13_ANTG4,PLZ8_BAUMAX,EWDICHTE,PLZ8_ANTG4 which were the top7 features of it.All of them meaned the cars level.
The component 2 contained D19_GESAMT_ANZ_24,D19_GESAMT_ANZ_12 which were the top2 features of it.All of them meaned household and family homes.
I suggest the cluster 3,5,6,7,8,9,15 of the general population that are more likely to be part of the mail-order company's main customer base.

## Conclusion
The difficulty of the dataset in this project is that there are many dimensions, the description of each dimension is not clear, and the difficulty of cleaning is relatively large.
There are many features in this project that belong to category features. The use of PCA for dimensionality reduction is not particularly good. The Kmeans algorithm is not particularly effective for such features. The next step is to try AUTOENCODING and K-prototype.