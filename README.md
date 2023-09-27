# Google_Data_Analytics_Case_Study_Cyclistic
Capstone Project for Google Data Analytics Certificate
## Introduction:
In this Case study I will perform the tasks of a junior data analyst at a fictional bikeshare company, Cyclistic, using real world data. By following the Data-Driven Decision-Making Process: Ask, Prepare, Process, Analyze, Share and Act, to answer business questions.
## Contents
Data Source: [divvy-tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html)

SQL Queries:
1. [Query 1 Combining Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%201%20Combining%20Data)
2. [Query 2 Exploring the Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%202%20Exploring%20the%20Data%20(SQL))
3. [Query 3 Cleaning the Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%203%20Cleaning%20the%20Data%20(SQL))
4. [Query 4 Analyze the Data](https://github.com/DanHoffman1/Google_Data_Analytics_Case_Study_Cyclistic/blob/main/Query%204%20Analyze%20the%20Data-%20(SQL))

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
