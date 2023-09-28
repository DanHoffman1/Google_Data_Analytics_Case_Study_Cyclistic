# Google Data Analytics Case Study Cyclistic
Capstone Project for Google Data Analytics Certificate
## Introduction:
In this Case study I will perform the tasks of a junior data analyst at a fictional bikeshare company, Cyclistic, using real world data. By following the Data-Driven Decision-Making Process: [Ask](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/README.md#Ask), [Prepare](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/README.md#prepare), [Process](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/README.md#process), [Analyze](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/README.md#analyze), [Share](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/README.md#share) and Act, to answer business questions.
## Contents
Data Source: [divvy-tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html)

SQL Queries:
1. [Query 1 Combining Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%201%20Combining%20Data)
2. [Query 2 Exploring the Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%202%20Exploring%20the%20Data%20(SQL))
3. [Query 3 Cleaning the Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%203%20Cleaning%20the%20Data%20(SQL))
4. [Query 4 Analyze the Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%204%20Analyze%20the%20Data-%20(SQL))

Data Visualizations [Tableau](https://public.tableau.com/app/profile/daniel.hoffman8788/viz/CyclisticCaseStudy_16953515488350/Dashboard1#1)

## Background
### Cyclistic
Cyclistic is a bike-share company in Chicago with different cycling offerings.  The program has grown to a fleet of 5,824 bicycles locked into a network of 692 stations across Chicago. Cyclistic strives to be inclusive with their types of bikes including traditional bicycles, hand cylcles, reclining cycles, and cargo cycles for those who cannot use a standard 2 wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use them to commute to work each day.

Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members.

Cyclistic’s finance analysts have concluded that annual members are much more profitable than casual riders. Although the pricing flexibility helps Cyclistic attract more customers, Moreno believes that maximizing the number of annual members will be key to future growth. Rather than creating a marketing campaign that targets all-new customers, Moreno believes there is a very good chance to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs.

Moreno (fictional director of marketing, and my boss) has set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the marketing analyst team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.

### Scenario
I will be assuming the role of a Junior Analyst on the Marketing Analyst Team in the company Cyclistic. The goal is to maximize annual memberships amongst riders. The director of marketing has tasked me with identifying how members and casual riders use Cyclistic's services differently. My insights will guide the marketing team to create a new marketing strategy to convert causual riders to annual members. To approve the new markeing strategy, executives at cyclistic will require compelling visuals and  data insights.

## Ask
### Business Task
Devise marketing strategies to convert casual riders to members.
### Analysis Questions
Three questions will guide the future marketing program:  
1. How do annual members and casual riders use Cyclistic bikes differently?  
2. Why would casual riders buy Cyclistic annual memberships?  
3. How can Cyclistic use digital media to influence casual riders to become members?

Moreno has assigned me the first question to answer: How do annual members and casual riders use Cyclistic bikes differently?

## Prepare
### Data Source
I will be using the most recent 12 months, July 2022 - August 2023 of data from the data source to create the most actionable and relevant insights. Data was accessed by downloading files from [divvy-tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html) The data has been made available by Motivate International Inc. under this [license](https://divvybikes.com/data-license-agreement).

This is public data that we can use to explore how different customer types are using Cyclistic bikes. But note that data-privacy issues prohibit us from using riders’ personally identifiable information. This means that we won’t be able to connect pass purchases to credit card numbers to determine if casual riders live in the Cyclistic service area or if they have purchased multiple single passes.

### Data Organization
The Data files have a title in the form of YYYYMM-divvy-tripdata. I am using 12 of them where each contains the data of one month with the following information, the ride id, bike type, start time, end time, start station, end station, start location, end location, and whether the rider has a membership or not. The corresponding column names are ride_id, rideable_type, started_at, ended_at, start_station_name, start_station_id, end_station_name, end_station_id, start_lat, start_lng, end_lat, end_lng and member_casual.

## Process
Bigquery was used to combine and clean 12 csv files.

Reason: 
Due to the volume of data. With each month of data containing several hundred thousand rows a large amount of data would need to be analyzed without losing values.

### Combine Data
SQL Query: [Query 1 Combining Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%201%20Combining%20Data)

12 csv files were uploaded to Google Cloud Storage to be combined and cleaned in Bigquery. These files were loaded into the dataset "cyclistic_data" and combined into a single table named "combined_data" with 5,723,606 rows for a full year.

### Data Exploration
SQL Query: [Query 2 Exploring the Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%202%20Exploring%20the%20Data%20(SQL))
Before cleaning the data, I need to familiarize myself with the types of data I would be working with. This also allowed me to find any errors and inconsistencies.

Observations:
1. The table below displays the column names and data types. **ride_id** is the primary key.

![combined table details](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/fdabf94e-30d0-4bb0-83a1-60fa8a2897b1)

2. The table below displays the number of  **null values** in each column

![combined table null values](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/032943ae-2636-40a2-a243-b887f690a30b)
Several columns were found to have missing data, including starting_station id and name, ending_station id and name as well as the ending longitude and latitude.

3. I then queried to find out if there were any **duplicate** rows in the ride_id column which would indicate duplicate rows of data that would need to be cleaned. No duplicates were found.

![Duplicate rows query](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/d7930a27-a1d1-4200-b9a2-c4fa39131200)

4. Next the length of the primary key, **ride_id**, was checked to make sure that all of the entries had the correct length. This was done to ensure that none of the rider ids were incomplete indicating an error in entry.

![ride_id length](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/06d3e735-63c9-4ee3-8ed9-83f897012972)

All rows were found to have a length of 16 meaning all ids were correctly entered into the dataset.

5. The **rideable_type** was checked to see how many types of bike were used.

![rideable_type](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/9d1c4f83-3b7c-4ac5-91a8-312394351352)

3 Types of bike were used; Electric, Classic, and Docked.

6. Next **started_at** and **ended_at** were queried to identify the format used for the start and end time for each trip. YYYY-MM-DD hh:mm:ss UTC format was used.

7. Trip duration was then checked. I specifically looked to find how many trips were shorter than a minute or longer than a day because those would need to be removed in the cleaning step. 5292 trips were longer than a day, and 153,165 trips were shorter than a minute.

8. The number of rows with **null values** was then checked. I took the count of **null values** in **start_station_name** or **start_station_id**, and the **null values** in **end_station_name** or **end_staton_id**. There were 868,904 missing values for start location to be remvoed and 925,149 missing values for end location to be removed.

9. **end_lat** and **end_lng** were also checked for the number of **null values** that would need to be removed. 6,102 were null.

10. Lastly the **member_casual** column was checked to make sure only the entries of either **member** or **causal** were in the dataset. No other entries were entered, no cleaning of this column was required.

![member casual](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/06b36161-e957-4f1e-8526-07a5ce76f01c)

### Data Cleaning
SQL Query: [Query 3 Cleaning the Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%203%20Cleaning%20the%20Data%20(SQL))

1. 3 new rows were created: **day_of_week**, **month**, and **ride_length**
2. All rows with **null values** were removed.
3. **ride_length** of less than a minute or longer than a day were removed.
4. Total of 1,474,260 rows removed during data cleaning.

## Analyze
SQL Query: [Query 4 Analyze the Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%204%20Analyze%20the%20Data-%20(SQL))

1. Query to find the number of trips per day made by members vs casual riders.
2. Query to find the number of trips per month made by members vs casual riders.
3. Query to find the number of trips per hour made by members vs casual riders.
4. Total number of trips made by members vs casual riders.
5. Query to find the number of trips by bike type made by members vs casual riders.
6. Query to find average duration by month by members vs casual riders.
7. Query to find average duration by day by members vs casual riders.
8. Query to find number of trips by starting station by members vs casual riders.
9. Query to find number of trips by ending station by members vs casual riders.
10. Query to find number of trips by starting location by members vs casual riders.
11. Query to find number of trips by ending location by members vs casual riders.

## Share
Data Visualizations [Tableau](https://public.tableau.com/app/profile/daniel.hoffman8788/viz/CyclisticCaseStudy_16953515488350/Dashboard1#1) 

Tableau was used for compelling visualizations as Bigquery was not able to make graphs or other visualizations.

The analysis question is: How do annual members and casual riders use Cyclistic bikes differently?

First I compared the duration of rides per day of the week, and month

![rides by day](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/59592b88-6126-46c9-befa-99bf7d6970d2)
![duration by months by member vs casual](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/029cc8e8-96aa-4c93-86d2-f2ad2fe23294)
 
Note that casual riders tend to ride for about twice as long as members, this could be due to a longer commute, a more recreational use of the bikes, or a longer distance trip. The members are consistent through the business days of the week, indicating a regular commute, and this also shows a consistent use through all months of the year with a slight increse through the warmer months. There is also an increase in both members and causal riders on weekends which could indicate recreational use. Casual riders also see a large increase in duration during the warmer months which would be consistent for Chicago as you would not want to ride a bike in the winter recreationaly, but would use it more recreatinaly in the warmer months.

Next I compared the number of trips by day, month and time of day by members vs. casual riders.

![Trips over time](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/cbce8788-3811-4179-a03d-36ad4f23bb81)

**Day of the week** From this graph we can see that no matter the day, members take more trips than casual riders. Members take more trips during business days and less on the weekends. Casual riders have the opposite trend. 

**Time of day** From this graph we can see members are mostly commuters, with number of trips peaking during rush hour times. Casual riders consistently increase the number of trips throughout the day and then decrease in the late hours/early morning hours of the day.

**Month** From this graph we see that members take more trips thoughout the year than casual members. However they both have the same trend of increasing number of trips as the weather warms up and then decreases after September as the weather gets colder.

We can infer from these observations that members may be using bikes for commuting to and from the work in the week days while casual riders are using bikes throughout the day, more frequently over the weekends for recreation purposes. Both are most active in summer and spring.

Next I show what types of bikes members use vs casual riders.

![Rideable type](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/2e71e2c8-4e27-4482-9755-d733e445e4fe)

From this bar graph we can see that overall members and casual riders prefer the classic bikes. Casual members are the only type that use the docked bikes and not very often, and both members and casual riders use the electic bikes a lot, but not as much as the classic bike. Overall the members take more trips than the casual members.

Next I compare starting locations for members and casual riders.

![starting locatoin](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/5aecd178-ef29-467d-99ca-abd6e9bcadb4)

The maps show how the casual riders tend to concentrate more in the downtown area when starting their trips, Especially near attractions and recreation areas such as the Navy Pier. Members are not so concentrated, being more spreadout with their starting location.

Lastly I compared the ending locations for members and casual riders.

![Ending location](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/assets/137096478/2786331c-9309-4ec9-b3b9-d77d5bc100fc)

The maps here show the same trend as the starting locations map. Casual riders are more concentrated in the downtown near attractions, members are more spreadout.

Summary:
  
|Casual|Member|
|------|------|
|Prefer using bikes throughout the day, more frequently over the weekends in summer and spring for recreation activities.|Prefer riding bikes on week days during commute hours (8 am / 5pm) in summer and spring.|
|Travel 2 times longer but less frequently than members.|Travel more frequently but shorter rides (approximately half of casual riders' trip duration).|
|Start and end their journeys near downtown recreational sites.|Start and end their trips close to universities, residential and commercial areas.| 
