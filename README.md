# World Life Expectancy

### Project Overview

This project consists of two phases: Data cleaning and EDA. By analyzing various aspects of the world life expectancy data, we seek to identify trends and provide valuable insights into public health and socioeconomic factors that influence longevity.

### Data Sources
World Life Expectancy Data: The primary dataset used for this analysis is the "WorldLifeExpectancy.csv" file, containing detailed information about different countries made by  the World Health Organization.

### Tools

- PostgreSQL - Data Cleaning and Analysis

### Data Cleaning/Preparation

In the initial data preparation phase, I performed the following tasks:

- Data loading and inspection.
- Handling duplicated rows.
- Handling missing values.

### Exploratory Data Analysis

EDA involved exploring the data to answer key questions, such as:

- What is the overall Life Expectancy trend?
- Which countries have the highest life expectancy
- What is the highest death cause?

### Data Analysis
 - interesting codes, findings ...

```sql
SELECT country, ROUND(AVG("life expectancy"),1) AS "life_expectancy",AVG("BMI") AS average_BMI
FROM public."world_life_expectancy_Staging"
WHERE "life expectancy" != '0'
AND "BMI" > 0
GROUP BY country
ORDER BY average_BMI ASC;

SELECT country, 
MIN("life expectancy") , 
MAX("life expectancy"), 
ROUND(MAX("life expectancy") - MIN("life expectancy"), 1) AS life_increase_15_years
FROM public."world_life_expectancy_Staging"
GROUP BY country
HAVING MIN("life expectancy") != '0'
  AND MAX("life expectancy") != '0'
order by life_increase_15_years ASC;

```
### Results/Findings

The analysis results are summarized as follows:
...

### Recommedtanions


  
