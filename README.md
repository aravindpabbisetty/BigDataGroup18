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
