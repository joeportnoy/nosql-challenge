# NoSQL Challenge: UK Food Hygiene Database

## Overview

The UK Food Standards Agency evaluates various establishments across the United Kingdom, assigning them food hygiene ratings. This project involves setting up a NoSQL database, performing updates, and analyzing the data to help the magazine *Eat Safe, Love* identify food establishments of interest.

## Table of Contents

- [Repository Structure](#repository-structure)
- [Part 1: Database and Jupyter Notebook Set Up](#part-1-database-and-jupyter-notebook-set-up)
- [Part 2: Update the Database](#part-2-update-the-database)
- [Part 3: Exploratory Analysis](#part-3-exploratory-analysis)
- [Requirements](#requirements)
- [Conclusion](#conclusion)

## Repository Structure

```
nosql-challenge/
├── Resources/
│   ├── establishments.json
├── NoSQL_analysis_starter.ipynb
├── NoSQL_setup_starter.ipynb
├── README.md
```

## Part 1: Database and Jupyter Notebook Set Up

1. Import the data from `establishments.json` using the following command in your terminal:
   ```bash
   mongoimport --db uk_food --collection establishments --drop --file establishments.json --jsonArray
   ```
2. Install and import required libraries: `pymongo` and `pprint`.
3. Establish a MongoDB connection and confirm:
   - The database `uk_food` is created.
   - The collection `establishments` exists.
   - A sample document is retrieved using `find_one()`.
4. Assign the `establishments` collection to a variable.

## Part 2: Update the Database

1. **Insert New Restaurant:** Add a new halal restaurant, "Penang Flavours," with the provided details.
2. **Update BusinessTypeID:**
   - Retrieve the `BusinessTypeID` for "Restaurant/Cafe/Canteen."
   - Update "Penang Flavours" with the correct `BusinessTypeID`.
3. **Remove Dover Establishments:**
   - Count the number of establishments in "Dover Local Authority."
   - Remove all establishments in Dover.
   - Verify the deletion.
4. **Data Cleanup:**
   - Convert latitude and longitude values to decimal numbers.
   - Convert `RatingValue` to integers.

## Part 3: Exploratory Analysis

1. **Hygiene Score Analysis:**
   - Find establishments with a hygiene score of 20.
   - Display the count and first result.
   - Convert results to a Pandas DataFrame.
2. **Highly Rated Establishments in London:**
   - Find establishments with `RatingValue` >= 4.
   - Use regex to filter locations containing "London".
   - Display count, first result, and convert results to a Pandas DataFrame.
3. **Top 5 Establishments Near "Penang Flavours":**
   - Identify establishments within 0.01 degrees of latitude/longitude.
   - Sort results by hygiene score in ascending order.
   - Display results and convert to a DataFrame.
4. **Hygiene Score by Local Authority:**
   - Count establishments with `HygieneScore = 0` for each Local Authority.
   - Sort by count in descending order.
   - Display the top 10 Local Authorities.

## Conclusion

This project provides an in-depth analysis of food hygiene ratings using NoSQL databases. By successfully setting up a MongoDB database, modifying the dataset, and conducting exploratory analysis, we can extract valuable insights for *Eat Safe, Love*. The ability to efficiently query and process data helps identify establishments that meet high hygiene standards and pinpoint areas of concern. Future improvements could include incorporating additional data sources or implementing real-time updates for ongoing analysis.