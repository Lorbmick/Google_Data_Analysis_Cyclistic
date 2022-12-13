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

Next, we load each data set per month with the read_csv function.  This will give us 12 different data frames.  It will be important to merge all of files into a single data frame to avoid repeating the same process for each month.
(insert picture)
After creating the single file, it is important to check for missing values. We want to check for missing values in order to make sure if further analysis is needed. Once we have created the single file (cycle_trips) then we can check for missing values. The results show columns with missing values are those related to the correspondent stations. The main analysis is based on the other columns with no missing values. This implies that the final conclusions and recommendations of this case study will not be biased. The creation of new columns necessary for this analysis. The main variable created is minutes_ride_length. This represents the difference in minutes between the time of start and end of each ride. The other additions are date variables such as month, year and day of the week.

Removing bad data
The last step in this cleaning process is removing data that does not match the following criteria:

minutes_ride_length needs to be a positive value thats greater than zero.
start_station_name and end_station_name can not be recorded as a blank space. 
These results assure these conditions are consistent and reliable.

Final Data
There are nwo two separate data structures obtained from the cleaning process:

start_at_info: summarizes the top 200 start stations, based on the total number of rides (either by casual customers or members)
Cycle_trips_v3: Cyclistic's cleaned trip data

The Data Analysis

The comparison between both types of customers indicates annual members have a lower average ride length compared to casual customers. The difference is about 20 minutes. This could indicator each group is using the bikes for different uses. The next visualizations support this theory. Plot 1 shows that the number of rides by annual members were almost uniform since October 2021. The upwards trend between April 2022 and July 2022 could be caused by the increase in warmer weather and effects of the Covid-19 pandemic infections decreasing. Plot 2 shows a very clear peak of the number of rides by casual members between the months with the highest temperatures in a year. Colder months such as October, November and December show a decrease most likely due to the drop in tempreture in Chicago. 
![Rplot](https://user-images.githubusercontent.com/119776629/207239370-6ebb381f-39ba-4db3-aa83-01f1f8097016.png)
![Rplot02](https://user-images.githubusercontent.com/119776629/207240664-b8bf0e10-a465-4ba0-b111-6729f8213082.png)

The evidence shows that annual members may have more purpose for their rides. Weather factors alone could not explain the consistent bike ride times for members. Plot 3 shows average ride length in minutes for members is consistent across the graph. The graphic shown for asual customers implies their rides can vary greatly for reasons such as pleasure, tourism, communting, etc.
![Rplot03](https://user-images.githubusercontent.com/119776629/207242829-51e3a65a-7cf3-43ed-9b91-8f11be9b9cb4.png)
A different perspective of these results can be obtained if the analysis is based on the days of the week. Plot 4 shows that the members are more likely to take a ride during weekdays, which does not happen during the weekends.

Moreover, for the members the average ride duration is constant throughout the week, with a very slight increase on Saturday and Sunday (View Plot 5). This could mean that they take these rides mainly to commute to their workplaces (or educational centers), but also that even this group is likely to take a ride just for leisure (given the fact that they do not have to pay extra for these situations). On the contrary, the numbers of casual customers are much larger during the weekends, which implies a predominance of bike rides for tourism or leisure
