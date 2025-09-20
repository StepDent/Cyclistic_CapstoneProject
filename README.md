Introduction

I am carrying out this case study as part of the capstone project for Coursera's Google Data Analytics, 
in order to answer the business questions qithin this case study I will follow google's data analysis 
process of Ask, Prepare, Process, Analysis, Share and Act.

Dataset link: https://divvy-tripdata.s3.amazonaws.com/index.html

Background

i am a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share
company in Chicago. The director of marketing believes the company’s future success
depends on maximizing the number of annual memberships. Therefore, your team wants to
understand how casual riders and annual members use Cyclistic bikes differently. From these
insights, your team will design a new marketing strategy to convert casual riders into annual
members. But first, Cyclistic executives must approve your recommendations, so they must be
backed up with compelling data insights and professional data visualizations.
Characters and teams

Cyclistic: A bike-share program that features more than 5,800 bicycles and 600
docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand
tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities
and riders who can’t use a standard two-wheeled bike. The majority of riders opt for
traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more
likely to ride for leisure, but about 30% use the bikes to commute to work each day.

Lily Moreno: The director of marketing and your manager. Moreno is responsible for
the development of campaigns and initiatives to promote the bike-share program.
These may include email, social media, and other channels.

ASK

To acheive our business goals Lily Moreno has provided three questions which will guide the future marketing program:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

I have been assigned the 1st questions
1. How do annual members and casual riders use Cyclistic bikes differently?

My Business Task
In support of the upcoming marketing campaign, I will be analysing the previous 12 months’ 
worth of trip data to identify trends and provide insight into the behaviours of casual riders 
and annual members. I will provide recommendations based on my findings to help convert casual riders 
into annual members.

PREPARE

In this project I will be using historical data for 2023 that cover annual and casual rider’s 
trips with Cyclistic bikes. I have 12 spreadsheets that hold each month’s trips with 13 columns in 
each that provide unbiased data on the trips taken - start and end time, start station name and end 
station name along with unique identifier for each trip. 

Unique customer identifier information like names, addresses, and age has been withhold providing an 
unbiased view of the information. 


Process

For this project I decided to use a combination of Excel, SQL and Power BI.

Excel: Familarise myself with the data, identify inconsistencies, add columns (ride_length, day_of_week,Month)
SQL lite: Analyse data
Power BI: Visualise Data

I used SQL as my main tool as the combined row value of the 12 datasets exceeded the amount possible in one excel spreadsheet,
SQL lite allowed me to combine all 12 spreadsheets into one from which i could then run the required data analysis. 

Total Rows: 5,719,877

As part of the data cleaning prcoess I removed the following Null values and trips that do not have any trip length. 

Rows with no trip length: 85058 

Null values

start_station_name - 875716

start_station_id - 875848

end_station_name - 929202

end_station_id - 929343

end_lat - 6990

end_lng - 6990

Final row count: 4,282,634


<img width="319" height="100" alt="image" src="https://github.com/user-attachments/assets/d27306cf-8c74-43ef-a02d-c9e71db88852" />


<img width="319" height="100" alt="image" src="https://github.com/user-attachments/assets/dd19a055-03b4-4311-91fb-914edc535b18" />


Data Cleaning Steps taking
1. Added a ride_length column.
   
2. Added a month column.
   
3. Added a weekday column.
  
4. Cleaned datetime for Started_at and ended_at to match SQL lite built in format.

ANALYSE

<img width="452" height="271" alt="image" src="https://github.com/user-attachments/assets/44d18a0c-9fd3-4d78-ae2f-bb158a81b84c" />

> The sum of trips per user type

> Member trips make up nearly two thirds of cyclistic business.

<img width="452" height="186" alt="image" src="https://github.com/user-attachments/assets/3a15c279-6421-4fa2-b49f-075b5eb74fc8" />

> Three types of bikes classic, electric and docked bike.

> There is a clear preference for classic bike over electric bikes while casual riders have used docked bikes whereas members have not.

<img width="452" height="166" alt="image" src="https://github.com/user-attachments/assets/fb206681-ddac-44c9-9bc7-2fabfabec3fd" />

> There is an increase for both casual and member trips during the summer months. 

> Members take more trips each month, suggesting that membership does equal more usage across the year.

<img width="452" height="160" alt="image" src="https://github.com/user-attachments/assets/746ce585-6187-49f3-abbf-97f7d29145e8" />

> On average casual rider take longer trips while members take shorter trips. 

> Examining these two charts it suggests that members take short trips more frequently while casual riders take less trips but for much longer periods of time. 

<img width="452" height="207" alt="image" src="https://github.com/user-attachments/assets/29987837-42b6-4320-803b-79be8790726c" />

> Members are more likely take trips on weekdays

> Whereas casual riders take more trips on weekends than weekdays

<img width="451" height="199" alt="image" src="https://github.com/user-attachments/assets/3a745939-24a9-44ee-be6f-c4ce6d302f26" />

> Member riders have a consistent average trip length each day of the week

> Casual riders average is above 2 hours each day

> This suggests that casual riders use their bikes for leisure while members are using their bikes for commuting.

<img width="452" height="148" alt="image" src="https://github.com/user-attachments/assets/190b797d-5e41-4bbd-af6a-ed5296867175" />

<img width="452" height="148" alt="image" src="https://github.com/user-attachments/assets/6a8f9dd2-2322-463c-a547-da0fbd9bc6e0" />

> These two charts show the average time of day that casual and members use their bikes

> There is no significant difference between when casual and members use their bikes each day, although this similarity potentially shows that casual riders would be more likely to become a member.


SUMMARY

Casual riders 
- Prefer using cyclistic bikes on the weekend over a weekday.
- Take less trips on average but for longer periods of time.
- On average start their trips at similar times to member trips.

Member rides
- Preference for using their membership on a weekday
- Take more trips than casual members but for shorter periods of time
- Use their bikes on average before and after a standard working day.

After 















