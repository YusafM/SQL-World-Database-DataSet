📓 Yusaf Malik Data Technician Workbook – Week 3
Welcome to my Week 3 Data Technician SQL Workbook!
This document summarizes my approach, code, and problem-solving steps as I worked through the World Database SQL exercises.

Table of Contents
Introduction
Problem-Solving Approach
Key SQL Queries
Screenshots & Results
Challenges & Solutions
Resources
Introduction
This workbook documents my hands-on practice with SQL using the World Database.
The focus was on joining tables, filtering data, and performing basic analysis with SQL.

Problem-Solving Approach
Step 1: Understand the task requirements.
Step 2: Explore the database schema.
Step 3: Write and test SQL queries.
Step 4: Analyze and interpret the results.
Step 5: Troubleshoot and optimize queries as needed.
Key SQL Queries
Example 1: Querying Cities by Continent
SQL
SELECT city.name, continent
FROM city
RIGHT JOIN country ON city.countrycode = country.code
WHERE continent = 'Europe';
Replace with your explanation or output here.

Example 2: Countries and Their Capital Cities
SQL
SELECT country.name AS Country, city.name AS City, city.population AS Population
FROM city
LEFT JOIN country ON city.id = country.capital
WHERE capital IS NOT NULL
ORDER BY population;
Replace with your explanation or output here.

Example 3: Calculating Population Density
SQL
SELECT 
    SurfaceArea, 
    ROUND(Population / SurfaceArea, 2) AS PopulationDensity 
FROM  
    country 
WHERE  
    Population IS NOT NULL AND Population > 0 
ORDER BY  
    PopulationDensity ASC 
LIMIT 20;
Replace with your explanation or output here.

Example 4: Cities with Above-Average GDP Per Capita
SQL
SELECT   
    city.Name AS City,  
    city.CountryCode,  
    country.Name AS Country,  
    city.Population AS CityPopulation,  
    ROUND(country.GNP / country.Population, 2) AS GDPPerCapita  
FROM   
    city  
JOIN   
    country ON city.CountryCode = country.Code  
WHERE   
    country.Population > 0 AND country.GNP IS NOT NULL  
    AND (country.GNP / country.Population) > (  
        SELECT AVG(GNP / Population)  
        FROM country  
        WHERE Population > 0 AND GNP IS NOT NULL  
    )  
ORDER BY   
    GDPPerCapita DESC; 
Replace with your explanation or output here.

Screenshots & Results
Add any relevant screenshots or paste results below each code block for clarity.

Challenges & Solutions
List any problems you faced and how you solved them (e.g., syntax errors, logic bugs, data issues).
Resources
MySQL World Sample Database
SQL Tutorial
(Add more resources you found helpful)
