# Azure Movie Recommendation System

## Overview

This project implements a movie recommendation system using Azure services, with a pipeline orchestrating the data flow and processing. The pipeline includes the following key steps:

1. Data Ingestion
2. Data Validation
3. Data Processing
4. Model Training
5. Email Notification

## Pipeline Steps

### 1. Data Ingestion
- The pipeline starts by ingesting raw movie data from Azure Blob Storage.

### 2. Data Validation
- The ingested data is validated using Azure Databricks.
- Valid data is moved to a "validated" container in Azure Storage.
- Invalid data is moved to a "rejected" container for further analysis.

### 3. Data Processing
- Azure Databricks is used to process the validated data.
- This step includes data cleaning, transformation, and feature engineering.

### 4. Model Training
- The processed data is used to train a collaborative filtering model using the Alternating Least Squares (ALS) algorithm in Spark ML.
- This step generates personalized movie recommendations.

### 5. Email Notification
- A Logic App is integrated into the pipeline to send an email notification.
- This step informs relevant stakeholders about the pipeline's completion or any important outcomes as well as the recommanded movie.

## Key Technologies Used

- **Azure Data Factory**: For orchestrating the entire data pipeline.
- **Azure Blob Storage**: For storing raw, validated, and rejected data.
- **Azure Databricks**: For data processing and running Spark ML code.
- **PySpark**: Used within Databricks for data processing and model training.
- **Azure Logic Apps**: For sending email notifications upon pipeline completion.
- **Azure Key Vault**: For securely storing secrets and credentials used in the pipeline.
