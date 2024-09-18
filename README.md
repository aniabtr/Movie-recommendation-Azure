Overview 
The project implements a movie recommendation system using Azure services, with the pipeline orchestrating the data flow and processing. The pipeline includes the following key steps:
Data Ingestion
Data Validation
Data Processing
Model Training
Email Notification
Pipeline Steps
Data Ingestion:
The pipeline starts by ingesting raw movie data from Azure Blob Storage.
Data Validation:
The ingested data is validated using Azure Databricks.
Valid data is moved to a "validated" container in Azure Storage.
Invalid data is moved to a "rejected" container for further analysis.
Data Processing:
Azure Databricks is used to process the validated data.
This step likely includes data cleaning, transformation, and feature engineering.
Model Training:
The processed data is used to train a collaborative filtering model using the Alternating Least Squares (ALS) algorithm in Spark ML.
This step generates personalized movie recommendations.
Email Notification:
A Logic App is integrated into the pipeline to send an email notification.
This step likely informs relevant stakeholders about the pipeline's completion or any important outcomes.
Key Technologies Used
Azure Data Factory: For orchestrating the entire data pipeline.
Azure Blob Storage: For storing raw, validated, and rejected data.
Azure Databricks: For data processing and running Spark ML code.
PySpark: Used within Databricks for data processing and model training.
Azure Logic Apps: For sending email notifications upon pipeline completion.
Azure Key Vault: For securely storing secrets and credentials used in the pipeline.
This pipeline demonstrates an end-to-end ETL (Extract, Transform, Load) process combined with machine learning and automated notifications, showcasing the integration of multiple Azure services to create a comprehensive data solution.
