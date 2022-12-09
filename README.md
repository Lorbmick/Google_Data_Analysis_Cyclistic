# Google_Data_Analysis_Cyclistic

By Loren Mickelson
December 2022

Introduction
                                       
The following case study is the final portion of the [Google Analytics Certificiate](https://www.coursera.org/professional-certificates/google-data-analytics). The objective is to take what you have learned from the certificate course and perfrom data analysis on a selected case case. I have chosen to analyze the Cyclistic case study. In this case study, I am junior data analyst on the marketing team for a bike sharing company called Cyclistc in Chicago.

About Cyclistic 

Cyclistic is a bike sharing company based out of Chicago. It features more than 5800 bike and 600 stations. The bikes can be unlocked from one station and
returned to any other station at any time. Cyclistic offers flexibility of its pricing plans: single-ride passes, full-day passes,
and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers
who purchase annual memberships are Cyclistic members.

Task

The marketing analyst team needs the junior analyst to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. This analysis could affect future marketing campaigns

About the Data

Cyclistic collects data from the trips taken on their bikes, compiles them into monthly csv files, and provides the data for analysis. For the purposes of this study, the data between November 2021 and October 2022 was used.

Processing the Data

The processing stage was performed in RStudio. It is the proper tool to handle the files included in the dataset. It is important to note the same data processing can be done using SQL through Big Query.

Data Collection

The fist step is to load the libraries for the cleaning process. Tidyverse, lubridate, dplyr and ggplot2 are going to be used. 

Next, we load each data set per month with the read_csv function.  This will give us 12 different data frames.  it will be important to merge all of files into a single data frame to avoid repeating the same process for each month.
(insert picture)
After creating the single file, it is important to check for missing values. We want to check for missing values in order to make sure if further analysis is needed. 
