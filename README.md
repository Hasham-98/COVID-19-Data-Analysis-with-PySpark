# COVID-19 Data Analysis with PySpark

This project uses the "[NeurIPS 2020] Data Science for COVID-19 (DS4C)" dataset from Kaggle to perform data preprocessing and analysis using PySpark.
Dataset

We are using the PatientInfo.csv file, which includes the following columns:

    patient_id: Unique ID of the patient
    sex: Gender of the patient
    age: Age of the patient
    country: Country where the patient resides
    province: Province of the patient
    city: City of the patient
    infection_case: Case of infection
    infected_by: ID of who infected the patient
    contact_number: Number of people the patient has contacted
    symptom_onset_date: Date of symptom onset
    confirmed_date: Date of confirmation
    released_date: Date of release from isolation
    deceased_date: Date of death
    state: Status of the patient (isolated/released/deceased)

Project Overview

In this project, we aim to preprocess the dataset, handle missing data, perform various analyses, and extract valuable insights. The project workflow includes the following steps:

### 1. Set Up PySpark

    Initiate PySpark session using findspark.
    Load and cache the dataset using the Spark DataFrame API.

### 2. Data Exploration

    Display the first 5 rows of the dataset.
    Examine the schema and statistical summary of the dataset.

### 3. Handling Missing Data

    Count the number of null values in each column.
    Use the coalesce function to fill missing deceased_date values with the corresponding released_date.

### 4. Feature Engineering

    Calculate the number of days between confirmed_date and deceased_date for deceased patients.
    Create new columns:
        is_male: Boolean column indicating gender (True for male).
        is_dead: Boolean column indicating death (True for deceased).
        age: Remove the "s" suffix from age groups and convert them to integers.

### 5. SQL Queries Using PySpark

    Use SQL-style queries to:
        Count the number of patients who survived and those who did not.
        Analyze the number of males and females in the dataset.
        Perform further SQL-based preprocessing on specific columns.

### 6. Data Preprocessing (SQL-Based)

    Convert the age column to DOUBLE type using SQL commands.
    Select only specific columns for further analysis: ['sex', 'age', 'province', 'state'].

### 7. Final Data Cleaning

    Drop irrelevant columns like patient_id, contact_number, and others after deriving key insights.
