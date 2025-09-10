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
SELECT ride_length
FROM "2023_Cyclistic_Trips"
WHERE ride_length = '00:00:00';

- Delete trips with no ride length
DELETE 
FROM '2023_Cyclistic_Trips'
WHERE ride_length = '00:00:00';



--Starting from scratch 

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

-- view full dataset
SELECT * 
FROM "2023_Cyclistic_Trips";

--identify how many rides there were for each member type
SELECT
  member_casual,
  COUNT(*) as 'Member_rides'
FROM "2023_Cyclistic_Trips"
GROUP BY member_casual;

DELETE FROM "2023_Cyclistic_Trips"
WHERE ride_id NOT IN (
  SELECT MIN(ride_id)
  FROM "2023_Cyclistic_Trips"
  GROUP BY ride_id
);

SELECT ride_id, COUNT(ride_id) 
FROM "2023_Cyclistic_Trips"
GROUP BY ride_id
HAVING COUNT(ride_id) > 1;

SELECT 
  AVG(ride_length)
FROM "2023_Cyclistic_Trips"
WHERE ride_length > 0;


-- Find out if any ride_lengths were longer than 24 hours long
SELECT ride_length
FROM "2023_Cyclistic_Trips"
WHERE ride_length = '00:00:00';

SELECT COUNT(*)
FROM "2023_Cyclistic_Trips"
WHERE ride_id IS NULL OR ride_id = '';

-- finding amount of Nulls per row
SELECT
SUM(CASE WHEN ride_id IS NULL OR ride_id = '' THEN 1 ELSE 0 END) AS missing_ride_id,
SUM(CASE WHEN rideable_type IS NULL OR rideable_type = '' THEN 1 ELSE 0 END) AS missing_rideable_type,
SUM(CASE WHEN started_at IS NULL OR started_at = '' THEN 1 ELSE 0 END) AS missing_started_at,
SUM(CASE WHEN ended_at IS NULL OR ended_at = '' THEN 1 ELSE 0 END) AS missing_ended_at,
SUM(CASE WHEN start_station_name IS NULL OR start_station_name = '' THEN 1 ELSE 0 END) AS missing_start_station_name,
SUM(CASE WHEN start_station_id IS NULL OR start_station_id = '' THEN 1 ELSE 0 END) AS missing_start_station_id,
SUM(CASE WHEN end_station_name IS NULL OR end_station_name = '' THEN 1 ELSE 0 END) AS missing_end_station_name,
SUM(CASE WHEN end_station_id IS NULL OR end_station_id = '' THEN 1 ELSE 0 END) AS missing_end_station_id,
SUM(CASE WHEN start_lat IS NULL OR start_lat = '' THEN 1 ELSE 0 END) AS missing_start_lat,
SUM(CASE WHEN start_lng IS NULL OR start_lng = '' THEN 1 ELSE 0 END) AS missing_start_lng,
SUM(CASE WHEN end_lat IS NULL OR end_lat = '' THEN 1 ELSE 0 END) AS missing_end_lat,
SUM(CASE WHEN end_lng IS NULL OR end_lng = '' THEN 1 ELSE 0 END) AS missing_end_lng,
SUM(CASE WHEN member_casual IS NULL OR member_casual= '' THEN 1 ELSE 0 END) AS missing_member_casual,
SUM(CASE WHEN ride_length IS NULL OR ride_length = '' THEN 1 ELSE 0 END) AS missing_ride_length,
SUM(CASE WHEN day_of_week IS NULL OR day_of_week = '' THEN 1 ELSE 0 END) AS missing_day_of_week
FROM "2023_Cyclistic_Trips";

-- Deleted all trips with no ride length
DELETE 
FROM '2023_Cyclistic_Trips'
WHERE ride_length = '00:00:00';

-- Count type of bike used
SELECT
  rideable_type,
  COUNT(*) as 'ride_type'
FROM "2023_Cyclistic_Trips"
GROUP BY rideable_type;












