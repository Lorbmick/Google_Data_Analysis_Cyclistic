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

A different perspective can be obtained if we base the analysis on the days of the week. Plot 4 shows members are likely to take a bikes during weekdays. Weekend use is less than causal riders. For members, the average ride duration is constant throughout the week. A slight increase does show for weekends (View Plot 5). The data shows members use the bikes to commute to work or school. However, the numbers of casual customers are much greater during the weekends. This suggests a majority of bike rides are used for tourism or leisure.
![Rplot04](https://user-images.githubusercontent.com/119776629/207244348-66964a9c-47b7-41f5-b1c5-524c841eee3c.png)
![Rplot05](https://user-images.githubusercontent.com/119776629/207244392-0e844630-245e-4bfc-9cc4-b025ca6af716.png)

Clear differences on shown with the type of bikes each customer tends to choose. Casual customers do not seem to have a preference over classic or electric bikes. This can be seen in Plot 6. Rides on electric bikes do last longer (Plot 7). The reason could be e-bikes use always-on pedal-assist technology. Casual customers could use this feature more often since they are more likely to take a ride for tourism or leisure.  On the other hand, members seem to have a greater preference for classic bikes.The rides average duration is almost identical for both rideable types. Again, this could be a strong indicator members are more focused on commuting to work than for leisure. 
![Rplot06](https://user-images.githubusercontent.com/119776629/207516026-668e356a-30ee-49ef-b10a-4b01a9561eea.png)
![Rplot07](https://user-images.githubusercontent.com/119776629/207516065-3c2e7f05-5115-44c8-b866-ef1caf650de7.png)

Conclusion 

The case study's objective was to analyze the Cyclistic's historical trip data and identify the possible differences between annual members and casual customers. Two main conclusions can be obtained for each group:  Casual customers ride more frequently. They ride bikes for a longer period of time during warmer seasons. They are more active during the weekends. They have a preference for e-bikes.These results suggest casual customers are more focused on rides for leisure and tourism. 

Annual members seem to take rides regularly throughout the year. They are  more active during the weekdays. They do not have a preference for either electric or classic bikes. The results show annual members are more focused on commuting to their places of work. 

Some recommendations can be proposed based on the previous conclusions to convert casual customers to annual members: The present case study had the objective to analyze the Cyclistic's historical trip data and identify the potential differences between the annual members and casual customers. There are two main conclusions that can be obtained for each profile:

Casual customers ride more frequently and for a longer period of time during warmer seasons. They are more active during the weekends and have a preference for e-bikes (since these allow to take longer rides more easily). Also, they tend to start from stations closer to the coast. These results suggest that casual customers are more focused on rides for leisure and tourism, but other reasons cannot be ruled out, specially during the weekdays.

Annual members appear to take rides regularly throughout the year, with an expected slight decrease during colder months. Unlike casual customers, they are much more active during the weekdays, but do not have a preference for either rideable type. Also, the starting stations they choose are more diversified around the city, and not clustered inside a small area. The results suggest that annual members are more focused on commuting to their workplaces, but again other reasons cannot be ruled out, since the rides during the weekends are a bit longer.

Despite not being the main task for this case study, some recommendations can be proposed based on the previous conclusions to convert casual customers to annual members: Identify and create campaigns for the casual customers that took a single ride and try to get them commit to an annual membership. Adding newer stations within the city could motivate single riders to becomme members. Finally, offer more e-bikes at a greater number of stations. 

