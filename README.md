# Chicago-Socioeconomic-Crime-Data-Analysis
Analyzed Chicago socioeconomic, public schools, and crime datasets using SQL and Python.  The project explores crime patterns, income levels, poverty rates, school safety scores, and community hardship indicators.  Used SQL queries with filtering, grouping, aggregation, ordering, and subqueries to extract insights from relational data.

## Project Overview
This project analyzes Chicago crime, census, and public school data using SQL.  
The goal is to identify patterns related to crime, income, poverty, school safety, and community hardship.

## Tools Used
- SQL
- SQLite
- Python
- Pandas
- Jupyter Notebook

## Datasets
- Chicago Crime Data
- Chicago Census Data
- Chicago Public Schools Data

## Key Questions Answered
- How many crimes were recorded in the crime table?
- Which community areas have per capita income below $11,000?
- Which crimes involved minors or children?
- What types of crimes were recorded at schools?
- Which community areas have the highest poverty rates?
- Which community area is the most crime-prone?
- Which community area has the highest hardship index?
- What is the name of the community area with the highest number of crimes?

## Key SQL Skills Demonstrated
- SELECT statements
- WHERE filtering
- LIKE operator
- Aggregate functions: COUNT(), AVG(), MAX()
- GROUP BY
- ORDER BY
- LIMIT
- Subqueries

## Main Insights
- Community area 25 had the highest number of recorded crimes.
- Austin was the community area with the highest number of crimes.
- Riverdale had the highest hardship index.
- Riverdale, Fuller Park, Englewood, North Lawndale, and East Garfield Park had the highest poverty percentages.
- Crimes recorded at schools included battery, criminal damage, narcotics, assault, criminal trespass, and public peace violation.

## Project Status

This project is a completed exploratory analysis focused on identifying key patterns and relationships between crime and socioeconomic factors.

Further improvements may include additional visualizations and deeper statistical analysis.

## Analysis Preview

### Top Areas by Poverty
![Poverty](screenshots/top poverty areas.jpg)

### Most Crime-Prone Area
![Crime](screenshots/most crime prone area.jpg)

### Highest Hardship Index
![Hardship](screenshots/hardship index max.jpg)

### Low Income Areas
![Income](screenshots/low_income_areas.png)
## Sample SQL Query

```sql
SELECT COMMUNITY_AREA_NAME
FROM CENSUS_DATA
WHERE community_area_number = (
    SELECT community_area_number
    FROM CHICAGO_CRIME_DATA
    GROUP BY community_area_number
    ORDER BY COUNT(*) DESC
    LIMIT 1
);
