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
