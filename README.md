# ITCS 6100 Big Data Analytics for Competitive Advantage

## Deliverable 1:

### Group 18:<br>
### Team Members:<br>
Manasa Avula - 801307493<br>
Nikhita Sai Boyidapu - 801327682<br>
Srikar Chamarthy - 801317299<br>
Rachana Gullipalli - 801311637<br>
Aravind Pabbisetty - 801274519<br>

### Dataset Link: https://www.kaggle.com/datasets/jasfre/gcc-cyclistic-case-study-present-report-prompt
### Dataset Size: 3 GB
The chosen dataset is of a bike sharing company based in chicago called Cyclistic. The  dataset consists of information of all the rides taken using different types of bikes by various citizens recently during the period of 12/2021 to 11/2022. The data is stored in CSV files where there is an individual CSV file present for trips taken each month.

### Business Problem or Opportunity, Domain Knowledge:
The Cyclistic Bike Share dataset provides us with valuable information about the usage of bikes in the bike-sharing industry. A potential business problem or opportunity that this dataset could be used to address is the optimization of Cyclistic's marketing strategy to attract more riders and increase revenue. There are several factors that can affect bike ridership, including weather conditions, day of the week, and time of day. By analyzing the data, we could identify patterns and trends in rider behavior and preferences, such as the most popular start and end stations, peak riding times, and trip lengths. We can also find which type of bike is mostly used, electric, casual bike or docked bike. Analyzing these factors can help us identify patterns in the dataset and understand how they impact bike usage. For example, we might find that bike usage is higher on weekdays than weekends or the usage is higher in the morning than evening etc. This kind of analysis can help bike-sharing companies to make more bikes available during those times.
To conduct our analysis, we will be using AWS S3 to store the dataset's CSV files, Amazon Quicksight to create interactive visualizations, and Amazon Sagemaker for data preparation and analysis. By leveraging these powerful AWS tools, we can efficiently extract meaningful insights from the Cyclistic Bike Share dataset to drive business growth and enhance the overall bike-sharing experience.

### Research Objectives and Questions: 
1) Which bike type is most used among the casual ,docked and    electric bikes?
2) Which weekday is preferable for people to ride the bike?
3) What is the peak time during the weekday that people use the bike?
4) What types of bikes are preferred by different customer types?
5) What is the average time of ride for each bike type?
6) How does the demand for bike rides vary across different months and days of the week based on start date and time?
7) Is there a difference in the duration of rides between members and casual riders?
8) What will be the rate of customers preferring electric bikes in the next 5 years?
9) What will be the most demandable locations for the next 3 years?

### The full document of deliverable 1 is attached [here](https://github.com/aravindpabbisetty/BigDataGroup18/blob/main/Deliverable-1.pdf).<br>


## Deliverable 2:

### AWS Services used:
● S3: We have used S3 to create a bucket and store csv files of each month and also stored the combined csv file of all months.<br>
● Sagemaker: We have used the jupyter notebook in sagemaker for the data preparation.<br>
● QuickSight: We have used quicksight to create a dashboard of the data visualizations.<br>

### Data Understanding:

The chosen dataset consists of 1200000 records and 19 columns. Some of the Important columns include:<br>

ride_id: It is the unique identifier assigned to each ride taken.<br>
rideable_type: It consists of the type of bike used in the ride.<br>
start_station_name: It consists of the station name where the ride starts.<br>
member_casual: It describes the membership of the customer such as casual_member or member.<br>

There are other columns such as started_at_date, started_at_time, ended_at_date, ended_at_time, time_of_ride, end_station_name, start_lat, start_lng, end_lat, end_lng.

To understand the data we have used dataframe functions such as<br>
head(): To view the first five records<br>
info(): To view the information about the columns<br>
describe(): Gives a statistical description of the attributes<br>
shape(): To find the number of rows and columns in the dataframe.

### Data Preparation: 

Data Preparation is an important task when working with Big Data. To prepare the data we have the jupyter notebook in AWS SageMaker. While performing the data preparation we have done:
Dropping unnamed columns and checking columns having null values<br>
Replacing null values with mode value of respective columns and checking is still null values exists<br>
Dropping the Duplicate rows.<br>
Adding a new column rideable_type_value that stores the categorical variable (rideable_type) as a numeric value.<br>
Adding a new column weekday for the started date.

### Exploratory Data Analysis:

We have done exploratory data analysis for our dataset with the help of jupyter notebook provided by AWS SageMaker. We have done various analysis such as finding skew of numeric columns, word cloud for most visited destination, rides taken each day of the week, correlation between longitude, distribution of bike types. This analysis helped us to understand and find patterns within the dataset, outlier detection and identify interesting correlations among the columns.

### Dashboard:

We have created a dashboard that consists of various types of informative and useful visualizations with the help of AWS Quicksight. The dashboard has the following visualizations: Vertical Bar Graph, Horizontal Bar Graph, Pie Chart, Line Chart, Tables and many other.

From the created dashboard we can find insights such as Member customers take rides for a longer period of time, Classic bike is most rented by customers followed by electric and docker bike, Type of Bike preferred in various stations, Ratio of customers returing the bike at each hour, highest ride time and most customer type at each station. The Visualization Dashboard are attached in the document.

### The full document of deliverable 2 is attached [here](https://github.com/aravindpabbisetty/BigDataGroup18/blob/main/Deliverable-2.pdf).

## Deliverable 3:
### 7)  Analytics, Machine Learning
We have used two ml models random forest classifier and k means clustering to get the insights from the dataset. By using random forest classifier we were able to predict which type of bikes will be preferred in the next few years.
![image4](https://user-images.githubusercontent.com/112770055/236347052-20602e82-5396-4a74-9018-fbdbf16a5a95.png)

From the above image we can see that the preferred bike is a classic bike. We have also predicted the most demandable location(hotspot) using k-means clustering model and we were able to identify 7 hotspots around the city. The below image shows those locations.
![image3](https://user-images.githubusercontent.com/112770055/236347201-db88cadb-dbf2-4000-be86-3bb90b07e3fe.png)
![image6](https://user-images.githubusercontent.com/112770055/236347215-a1a2ca46-931a-45cb-8a44-139bec96a12f.png)

### 8) Evaluation and Optimization

We have evaluated the K-means Clustering model performance by checking whether the clusters are loosely or tightly coupled. In case of clustering models inertias and silhouette_scores are the parameters that evaluate the model performance. Using these scores we can find the optimal number of clusters required to do clustering. So we have optimized the model based on the optimal number of clusters and we can see a change in the number of clusters. The clusters are clustered in such a way that the points that are mostly similar and have too much variation with other clusters are placed in the same cluster.
Most demandable locations/ hotspots after model Optimization
![image10](https://user-images.githubusercontent.com/112770055/236347298-4948d463-c2ab-49a1-b57c-815d46f93540.png)

### 9)  Results
#### Which bike type is most used among the classic ,docked and electric bikes?
![image8](https://user-images.githubusercontent.com/112770055/236347379-0da48491-04f8-4012-b2a9-e9e8f62fe8e6.png)
From the above graph we can say that classic bikes are most used.

#### Which weekday is preferable for people to ride the bike?
![image1](https://user-images.githubusercontent.com/112770055/236347462-71765445-7f6f-4029-bd1f-f0d025af3b42.png)
From the above graph we can see that thursday is more preferable for people to ride the bike

#### What is the most used end station for returning the bike?
![image7](https://user-images.githubusercontent.com/112770055/236347545-c8a9177d-4fee-4e0d-964e-7b7e933ecb59.png)
From the above visualization we can see that Michigan Ave & Oak St is the most used end station to return the bike

#### What types of bikes are preferred by different customer types?
![image2](https://user-images.githubusercontent.com/112770055/236347615-bcb2a579-aa73-48e4-8432-0653102267cb.png)
From the above visualization we can see that members use classic bikes more and casual people use electric bikes more. 

#### How does the demand for bike rides vary across different months and days of the week based on start date and time?
![image9](https://user-images.githubusercontent.com/112770055/236347738-250aa5cd-a4df-4a0a-809f-9ca89feb2fb1.png)
This visualization shows the demand for bike rides vary across different months and days of the week. X-axis represents the day of the week and Y-axis represents the month. Most demand is on the Thursdays of december.

#### Is there a difference in the duration of rides between members and casual riders?
<img width="431" alt="image5" src="https://user-images.githubusercontent.com/112770055/236347783-28a57e37-e424-4169-ab06-58e9aa8921b1.png">
We can say that there is a difference in the duration of rides between members and casual riders. Members take rides for a longer duration of time.

#### What will be the most demandable locations for the next 3 years?
In the below visualization we can see the top most hotspot areas for the bike pickups. With this bike companies can increase their number of stations and bikes in those hotspots to meet the demand and increase their revenue.
![image3](https://user-images.githubusercontent.com/112770055/236347875-e6bb565a-d22b-47fa-96a5-a78d10dff958.png)

#### What will be the preferred bike in the next few years?
![image4](https://user-images.githubusercontent.com/112770055/236347913-9b0e94bd-fa7b-4c73-b4aa-f742163b20c3.png)
Using the model we were able to predict that for the next 5 years the preferred bike type is classic bike


### 10) Future Work, Comments - students may want to consider the following questions

#### 1) What was unique about the data?  Did you have to deal with imbalance? What data cleaning did you do? Outlier treatment?  Imputation?
* The dataset consists of unique attributes that describe the information of the trip such as trip duration, type of bike used, customer type, start and end stations. These features are helpful to analyze, derive various patterns. 
* These patterns are helpful for the Cyclistic company to forecast the future demand and ensure that they meet the demand by increasing the number of bikes or stations in the busiest localities.
* We have performed data cleaning by removing the null columns and removing duplicate entries. 
* We have detected outliers entries which are stations far outside and removed them.
* Next we found some null values in different attributes and imputed them by finding the mean for numerical attributes and finding the mode for categorical attributes.

#### 2) Did you create any new additional features / variables?
We have created some new features and added them to the dataset. We have encoded the Categorical variables such as member_type and bike type to numerical variables. Also we have added a new feature trip distance which is done by computing the distance between latitudes and longitudes of start and end point. 

#### 3) What was the process you used for evaluation?  What was the best result?
For the classification of which type of bike is most preferred we have used Random Forest Classifier. We have split the dataset into training and test dataset. With the training dataset we have trained the model and using the test dataset we were able to calculate the accuracy and able to predict which bike is preferred in the next 5 years. The model we have chosen is random forest classifier because the accuracy using this model is more compared to other models like the SVM classifier, Decision tree classifier. We have used Kmeans clustering to find the most demandable location. Using that we were able to create clusters where most rides are started and identified the hotspots in the city. We have evaluated it based on the clustering score and optimized the number of clusters.

#### 4) What were the problems you faced? How did you solve them?
The main challenge we faced was extracting the features that can be used to get the insights. We also had to clean a lot of data, remove null columns, duplicate rows, impute the null values and also detect, remove the outliers. We faced difficulties in choosing the right model for finding the predictions. We worked on different classification and clustering models, evaluated model accuracy and chose the best model to derive our predictions.

#### 5) What future work would you like to do?
In the future we would like to optimize the model, improve its performance, accuracy and derive many other useful insights and predictions that will be useful for the bike sharing organization while making decisions. So that they can provide much better services to its customers and stand ahead of their competitors.

#### 6) Instructions for individuals that may want to use your work?
* Requirements: Amazon S3, Amazon Sagemaker, Python, Jupyter Notebook 
* Packages: Numpy, Seaborn, Pandas, Matplotlib
* Steps to run:
  * The first step is to download the Cyclistic Dataset from Kaggle or from the link provided below. 
  * After downloading the dataset, create a S3 bucket to store the data in AWS. 
  * Upload the csv file that consists of Cyclistic data into the S3 bucket. 
  * Next with the help of Jupyter notebook in AWS Sagemaker, perform data understanding and cleaning, preparation activities such as removing duplicate values and    imputation null values and adding new features. 
  * Finally with the help of AWS Quicksight create useful visualizations and add them to the dashboard.

### Dataset link:
https://www.kaggle.com/datasets/jasfre/gcc-cyclistic-case-study-present-report-prompt

You can also copy the merged csv files of each month from the this link:

https://drive.google.com/file/d/1I-RdrIHhjEAKdMJM_P_zSjIVKHISg-2d/view?usp=share_link

### The full document of deliverable 3 is attached [here](https://github.com/aravindpabbisetty/BigDataGroup18/blob/main/Deliverable-3.pdf).<br>


