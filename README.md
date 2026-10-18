# Relational Databases - Final Project

## Project Description

This project focuses on working with relational databases using PostgreSQL.

The main tasks include importing a dataset, normalizing it to Third Normal Form (3NF), performing SQL aggregations, working with date functions, and creating custom SQL functions.

## Dataset

**Dataset:** `infectious_cases.csv`

**Source:** [Infectious Cases — Google Drive](https://drive.google.com/file/d/1dQf-uVXzYPYYGgXsG1y4Q1qDdhP2miZl/view)

The dataset contains:

- 10,521 records
- 245 unique entities (countries and regions)
- Data from 1920 to 2023
- Statistics on rabies, malaria, HIV, tuberculosis, polio, smallpox, cholera, and other diseases

Missing values are preserved as `NULL`.

## Tools

- PostgreSQL 16
- Google Colab
- Python
- SQLAlchemy
- pandas
- pgserver

## Completed Tasks

### Task 1. Data Import

Created the `pandemic` schema and imported the CSV dataset into the `infectious_cases` table using PostgreSQL `COPY`.

Checked the imported records, table structure, and missing values.

### Task 2. Database Normalization (3NF)

Normalized the original dataset into two tables:

- `pandemic.entities` — unique combinations of entity names and codes.
- `pandemic.infectious_cases_normalized` — disease statistics linked to entities through `entity_id`.

Added primary keys, a foreign key, and data integrity constraints.

Verified that all 10,521 records were preserved.

### Task 3. Data Analysis

Calculated `AVG()`, `MIN()`, `MAX()`, and `SUM()` for the `Number_rabies` column.

Grouped the results by entity, sorted by average value in descending order, and displayed the top 10 records.

### Task 4. Date Calculations

Used PostgreSQL functions `MAKE_DATE()`, `CURRENT_DATE`, `AGE()`, and `EXTRACT()` to create dates from years and calculate the difference in full years.

### Task 5. Custom SQL Functions

Created two custom PostgreSQL functions:

- `pandemic.years_since(input_year)` — calculates the number of full years since January 1 of the specified year.
- `pandemic.average_cases(cases_per_year, period_divisor)` — calculates the average number of cases per month (12), quarter (4), or half-year (2).

Both functions were tested and used with the dataset.

## How to Run

1. Open `FP.ipynb` in Google Colab.
2. Select **Runtime → Restart session and run all**.
3. The notebook installs the required libraries and starts PostgreSQL.
4. The dataset is downloaded and imported into the database.
5. All SQL queries, custom functions, and verification checks are executed.

## Repository Structure

```text
goit-rdb-fp/
├── FP.ipynb
├── README.md
└── screenshots/
    ├── task2_1.png
    ├── task2_2.png
    ├── task3_1.png
    ├── task4_1.png
    ├── task5_1.png
    └── task5_2.png
```

## Screenshots

Screenshots of the SQL queries and their results are available in the `screenshots` folder.

| Screenshot | Description |
|---|---|
| `task2_1.png` | Normalized entities table |
| `task2_2.png` | Normalized disease statistics |
| `task3_1.png` | Rabies statistics using aggregation functions |
| `task4_1.png` | Date calculations |
| `task5_1.png` | Custom function for calculating year differences |
| `task5_2.png` | Custom function for average disease cases |

## Results

The project demonstrates database normalization, SQL aggregations, date calculations, and reusable SQL functions in PostgreSQL.

All tasks were implemented in a Google Colab notebook with SQL queries, results, and verification checks.
