# Cyclistic_CapstoneProject
Google coursera capstone project - Cyclistic 

Combine 12 Months of cyclistic data into one table called '2023_Cyclistic_Trips' along with a basic Select query to explore data

CREATE TABLE '2023_Cyclistic_Trips' AS 
SELECT * FROM "Cyclistic_02_2023"
UNION ALL
SELECT * FROM "cyclistic_03_2023"
UNION ALL
SELECT * FROM "cyclistic_04_2023"
UNION ALL
SELECT * FROM "cyclistic_05_2023"
UNION ALL
SELECT * FROM "cyclistic_06_2023"
UNION ALL
SELECT * FROM "cyclistic_07_2023"
UNION ALL
SELECT * FROM "cyclistic_08_2023"
UNION ALL
SELECT * FROM "cyclistic_09_2023"
UNION ALL
SELECT * FROM "cyclistic_10_2023"
UNION ALL
SELECT * FROM "cyclistic_11_2023"
UNION ALL
SELECT * FROM "cyclistic_12_2023"
UNION ALL
SELECT * FROM "cyclistic_01_2024";
;

SELECT *
FROM '2023_Cyclistic_Trips'
;

-- Updating started_at and ended_at to correct format


-- Count of rows before any data cleansing
SELECT 
  COUNT(*) 
FROM "2023_Cyclistic_Trips"
;
*Result: 571,9877*

--identify how many rides there were for each member type
SELECT
  member_casual,
  COUNT(*) as 'Member_rides'
FROM "2023_Cyclistic_Trips"
GROUP BY member_casual;

-- Identify duplicates for ride ID
SELECT ride_id, COUNT(ride_id) 
FROM users
GROUP BY ride_id
HAVING COUNT(ride_id) > 1

-- Find the average ride length of each trip
SELECT 
  AVG(ride_length)
FROM "2023_Cyclistic_Trips";

-- Locate rides with no time length
SELECT ride_length, count(ride_length)
FROM "2023_Cyclistic_Trips"
WHERE ride_length = '00:00:00';
--85,058

-- Delete trips with no ride length
DELETE 
FROM '2023_Cyclistic_Trips'
WHERE ride_length = '00:00:00';
(Deleted 85,058 rows)

-- Count type of bike used
SELECT
  rideable_type,
  COUNT(*) as 'ride_type'
FROM "2023_Cyclistic_Trips"
GROUP BY rideable_type;

-- AVG ride duration for each member per Month
SELECT month, member_casual, AVG(ride_length) AS avg_ride_duration
FROM "2023_Cyclistic_Trips"
GROUP BY month, member_casual;

-- Max ride of ride_length
SELECT member_casual, MAX(ride_length)
FROM "2023_Cyclistic_Trips";
GROUP BY member_casual;

-- Most ride per day of the week 
SELECT day_of_week,
       COUNT(day_of_week) AS count_day
FROM "2023_Cyclistic_Trips"
GROUP BY day_of_week
ORDER BY count_day DESC;

-- Average ride length for casual and members
SELECT member_casual, AVG(ride_length) AS member_avg
FROM "2023_Cyclistic_Trips"
GROUP BY member_casual;


<img width="1204" height="518" alt="image" src="https://github.com/user-attachments/assets/751447c8-4794-4e87-bb76-f4e6ff1c5bf7" />













