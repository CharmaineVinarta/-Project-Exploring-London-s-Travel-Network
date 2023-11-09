# Project: Exploring London's Travel Network

## Overview

Welcome to the "Exploring London's Travel Network" project! In this project, we'll delve into London's extensive public transport system, managed by Transport for London (TfL). TfL oversees various modes of transportation, including the London Underground, buses, trams, river services, and more. We'll analyze public transport journey volume data to gain insights into London's travel network.

- Emirates Airline cable car link: https://en.wikipedia.org/wiki/London_cable_car
- The Mayor of London's office data link: https://data.london.gov.uk/dataset

## Data Source

Work with a modified dataset from the Mayor of London's office, available through a Snowflake database named TFL. The dataset, stored in the `TFL.JOURNEYS` table, contains information about public transport journeys, including:

- MONTH (Month in number format)
- YEAR (Year)
- DAYS (Number of days in the month)
- REPORT_DATE (Date of the report)
- JOURNEY_TYPE (Method of transport used)
- JOURNEYS_MILLIONS (Number of journeys in millions)

## Project Tasks

### 1. Most Popular Transport Types

Write a SQL query to identify the most popular transport types based on the total number of journeys. The output should include `JOURNEY_TYPE` and `TOTAL_JOURNEYS_MILLIONS`, sorted in descending order. Save the query as `most_popular_transport_types`.

### 2. Emirates Airline Popularity

Find the five months and years with the highest volume of travel on the Emirates Airline cable car. The output should contain `MONTH`, `YEAR`, and `ROUNDED_JOURNEYS_MILLIONS` (rounded to two decimal places). Exclude null values and save the result as `emirates_airline_popularity`.

### 3. Least Popular Years for the Tube

Identify the five years with the lowest volume of Underground & DLR journeys and save the result as `least_popular_years_tube`. The output should include `YEAR`, `JOURNEY_TYPE`, and `TOTAL_JOURNEYS_MILLIONS`.

## Getting Started

To access the Snowflake database, use the following SQL syntax: `FROM TFL.JOURNEYS` (ensure of using uppercase letters).

## How to Approach the Project

1. **Finding the most popular transport types**
   - Build a query to calculate the total number of journeys by transport type.
   - Use the `SUM()` function to calculate the total journeys.
   - Group the data by `JOURNEY_TYPE`.
   - Sort the results in descending order by `TOTAL_JOURNEYS_MILLIONS`.

2. **Identifying the most popular months and years for Emirates Airline cable car travel**
   - Write a query to identify the top five months and years for Emirates Airline travel.
   - Use the `ROUND()` function to round numeric values.
   - Filter the data for "Emirates Airline" using a `WHERE` clause.
   - Exclude missing values using `ROUNDED_JOURNEYS_MILLIONS IS NOT NULL`.
   - Limit the results to five rows and order them by `ROUNDED_JOURNEYS_MILLIONS` in descending order.

3. **Least popular years for the tube**
   - Create a query to find the five years with the lowest Underground & DLR journey volume.
   - Select `YEAR`, `JOURNEY_TYPE`, and `SUM(JOURNEYS_MILLIONS)`.
   - Use the `LIKE` operator to filter by `'%Underground%'`.
   - Group the data and order it by `TOTAL_JOURNEYS_MILLIONS` in ascending order.
   - Limit the results to five rows.

