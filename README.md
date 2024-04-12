# HACKERRANK.COM
HACKERRANK practice questions and answers


**Weather Observation Station 3**
Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

SELECT STATION.CITY
FROM STATION
WHERE MOD(ID, 2) = 0
GROUP BY STATION.CITY

**Weather Observation Station 4**
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

SELECT NUM_OF_RECORDS - UNIQUE_CITY_NAMES
FROM (
SELECT COUNT(CITY) AS NUM_OF_RECORDS,
COUNT(DISTINCT CITY) AS UNIQUE_CITY_NAMES
FROM STATION) AS DIFFERENCE

**Weather Observation Station 5**
Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

((select CITY,length(CITY) from STATION order by length(CITY),CITY limit 1 )
union 
(select CITY,length(CITY) from STATION order by length(CITY) desc limit 1) ORDER BY CITY);
