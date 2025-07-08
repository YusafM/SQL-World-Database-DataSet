# 🌍 SQL World Database DataSet

Welcome to the **SQL World Database DataSet** repository! This project contains curated datasets and resources related to the World Database, designed to help users practice SQL queries and data analysis skills. 🗃️

---

## 📑 Table of Contents

- [Project Overview](#-project-overview)
- [Key Features](#-key-features)
- [Sample Datasets](#-sample-datasets)
- [Getting Started](#-getting-started)
- [Problem-Solving Approach](#-problem-solving-approach)
  - [Querying Cities by Continent](#-querying-cities-by-continent)
  - [Finding Countries and Their Capital Cities](#-finding-countries-and-their-capital-cities)
  - [Calculating Population Density](#-calculating-population-density)
  - [Listing Cities with High GDP Per Capita](#-listing-cities-with-high-gdp-per-capita)
- [Other Approaches Used](#-other-approaches-used)
- [FAQ](#-faq)
- [Credits / Acknowledgments](#-credits--acknowledgments)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🚀 Project Overview

This repository provides SQL datasets and supporting materials for learning and practicing SQL. 
It highlights my approach to solving real-world database challenges, with detailed code examples, explanations, and visual aids to help others learn SQL effectively.

---

## ✨ Key Features

- 📂 Practice datasets for classic SQL exercises  
- 📝 Step-by-step problem-solving documentation  
- 💡 Example queries and solutions  
- 🔗 Useful resources and learning links  

---

## 📊 Sample Datasets

| File Name    | Description                      |
|--------------|----------------------------------|
| world.sql    | Main world database schema/data  |
| cities.csv   | List of world cities             |
| country.csv  | List of world countries          |
| ...          | (Add more as needed)             |

---

## 🏁 Getting Started

Follow these steps to get up and running with the SQL World Database DataSet:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/YusafM/SQL-World-Database-DataSet.git
Navigate to the project directory:
bash
cd SQL-World-Database-DataSet
Review the available data files:
(e.g., world.sql, cities.csv, etc.).
Set up your database environment:
Install MySQL or your preferred SQL database if you haven’t already.
Import the SQL schema/data into your database:
bash
mysql -u yourusername -p < world.sql
Connect to your database using your database client or command-line tool.
Start querying!
Use the provided SQL queries and examples in this README to explore and analyze the dataset.
🧩 Problem-Solving Approach
🛠️ Code Examples from My Problem-Solving Process:

🇪🇺 Querying Cities by Continent
To list all cities in Europe, I used a RIGHT JOIN to combine the city and country tables, filtering for the European continent:

SQL
SELECT city.name, continent
FROM city
RIGHT JOIN country
  ON city.countrycode = country.code
WHERE continent = 'europe'
📷 Picture:
Add a screenshot or diagram here to illustrate the output or process.
Querying Cities by Continent

🏙️ Finding Countries and Their Capital Cities
This query associates each country with its capital city and sorts the results by population:

SQL
SELECT country.name AS Country, city.name AS City, city.population AS Population
FROM city
LEFT JOIN country
  ON city.id = country.capital
WHERE capital IS NOT NULL
ORDER BY population
📷 Picture:
Add a screenshot or diagram here to illustrate the output or process.
Finding Countries and Their Capital Cities

🌍 Calculating Population Density
To find the countries with the lowest population density:

SQL
SELECT 
    SurfaceArea, 
    ROUND(Population / SurfaceArea, 2) AS PopulationDensity 
FROM  
    country 
WHERE  
    Population IS NOT NULL AND population > 0 
ORDER BY  
    PopulationDensity ASC 
LIMIT 20;
📷 Picture:
Add a screenshot or diagram here to illustrate the output or process.
Calculating Population Density

💰 Listing Cities with High GDP Per Capita
This query finds cities in countries whose GDP per capita is above average, showing how I used subqueries and calculated fields:

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
📷 Picture:
Add a screenshot or diagram here to illustrate the output or process.
Listing Cities with High GDP Per Capita

✨ Other Approaches Used
Step-by-step breakdowns:
Each problem is broken down into manageable steps, from understanding the requirements to writing and optimizing SQL queries.

Troubleshooting:
I recorded common issues faced (such as syntax errors or data inconsistencies) and described how I resolved them.

Learning resources:
Whenever I encountered difficulties, I referenced official documentation and community forums, noting the most helpful resources.

❓ FAQ
Q: What database system is this dataset designed for?
A: The provided SQL files are designed for MySQL, but can be adapted for other systems with minor adjustments.

Q: Can I contribute new queries or improvements?
A: Absolutely! See the Contributing section for details.

Q: Are there any prerequisites?
A: Basic knowledge of SQL and access to a SQL database system (e.g., MySQL) are recommended.

Q: What should I do if I find an error in the data?
A: Please open an issue or submit a pull request with the correction.

🙏 Credits / Acknowledgments
Data inspired by the classic MySQL World Sample Database.
Thanks to all contributors, educators, and the open-source community.
Special thanks to GitHub Copilot for assistance with code generation and documentation.
🤝 Contributing
Contributions are welcome! If you have new datasets, improved queries, or additional solutions, feel free to open a pull request or submit an issue.

📄 License
This project is open-source and available under the MIT License.
