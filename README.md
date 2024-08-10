# California House Price Prediction

#### OVERVIEW

In this application, I have selected a dataset from kaggle ("USA Real Estate Dataset") . The original dataset contained information on more than 2 million houses sold all over United States (2,226,382 entries). I have selected only houses sold in California state. The goal is to analyse data and predict the sale price of any particular house in California.

#### CRISP-DM Framework

![image](https://github.com/user-attachments/assets/88fa7e5f-2c8b-446f-be6f-fedacecededf)

To frame the task, throughout our this applications I have referred back to a standard process in industry for data projects called CRISP-DM. This process provides a framework for working through a data problem. 

#### Business Understanding

From a business perspective, we are trying to predict a price for a house based on various features of the house. We will be considering all the features which affect the house price in california.

Given is the USA Real Estate Dataset.

Understand the features and the data
Cleanup the data records and columns
Create the models which can predict the price of california house

#### Data Analysis and Preparation 

1.  Checked the value counts for states and realized that we have 227215 entries for California state. This will be sufficient data to build and compare various models.
2.  Dropped "brokered_by" column as it will not be useful for determining the price
3.  We will drop Street address and state anf use only zip_code feature.
4.  To use zip_code in a meaningful way, we have calculated average price of house for each zip code and added that as a new feature in the dataframe
5.  We will consider houses with prev_sold_date and consider only sold year in our feature list
6.  We filled acre_lot, bed, bath and house size with average values

##### Price Distribution : 

   ![image](https://github.com/user-attachments/assets/e359a065-096e-4f1b-be5c-8eca9917fa59)

##### House size distribution :

![image](https://github.com/user-attachments/assets/5a8d07eb-1d24-4d20-96df-b05179ea3528)


##### Sold year distribution :

![image](https://github.com/user-attachments/assets/d7fd0c7f-2c1b-45cb-b759-44fd0fa75de3)


##### Scatter plot of House Size Vs Price :

![image](https://github.com/user-attachments/assets/07dccdb2-e1ed-4503-bf92-69bc6ed0926b)


#### Modeling 

I have built and compared Linear Regression Model, Ridge Regression model and Lasso Regression Model. For Ridge and Lasso, I have used GridSearchCV to determine the best parameters.

Linear Regression Model : 

![image](https://github.com/user-attachments/assets/fa64c6f9-0d26-4af5-a7cd-f8850afeffff)


Traning data Actual Vs Prediction with Linear Regression :

![image](https://github.com/user-attachments/assets/9fd56ca5-7877-475f-aa05-1db1a5743567)


Test data Actual Vs Prediction with Linear Regression 

![image](https://github.com/user-attachments/assets/33ccb1be-91d5-4597-a87d-575333ada229)


Ridge Regression Model : 

![image](https://github.com/user-attachments/assets/a060088f-9527-4900-9c31-f7723ef82d08)


Traning data Actual Vs Prediction with Ridge Regression :

![image](https://github.com/user-attachments/assets/41015427-8264-4841-aeed-aa28dd999d38)


Test data Actual Vs Prediction with Ridge Regression :

![image](https://github.com/user-attachments/assets/ed76fe94-55bd-467c-a4f2-bdc011558bc6)


Lasso Regression Model : 

![image](https://github.com/user-attachments/assets/7c145cce-75b8-475a-8857-9ea210d4136a)


Traning data Actual Vs Prediction with Lasso Regression :

![image](https://github.com/user-attachments/assets/f6934957-4dd8-4ef2-a8f7-e93b2672df03)


Test data Actual Vs Prediction with Lasso Regression :

![image](https://github.com/user-attachments/assets/07674fbe-6317-4cc5-a153-1fbda1c7b362)


### Comparison of Models with respect to MSE :

![image](https://github.com/user-attachments/assets/3494b7fb-0dec-405d-809c-b248b71f381b)

### Importance of features for Linear Regression Model as it performed best amongst all three models for our case

![image](https://github.com/user-attachments/assets/7954ebde-d0ed-42ca-9e24-316f140b8ec5)

### Findings

· In California, the most important feature is Zip code (i.e. location of the house)
· House size is the second most important factor deciding the price of the house
· After house size number of beds and number of baths are important in deciding the price
· Surprisingly, according to the linear regression model, which performed best in this case, the lot size is least important feature in deciding the house price in california. 

### Next steps 

· To improve the performance of the model, outliers need to be cleaned up extensively.
· We can try to search a data with more features like Age of the house and may be the condition of the house (how well the house is upgraded/maintained etc)
· We can try Deep Leaning models to see if those perform better than traditional regression models.


   
