# Covid19_Prediction-Reporting
We will transform and make reports on the ECDC covid19 data. Azure Data Factory is used the most in this project.

<img width="1440" height  = "400" alt="Covid_19_Solution_Architecture" src="https://github.com/venkat2705/Covid19_Prediction-Reporting/assets/60357150/4ca116f9-0d61-47e3-be93-86c1fd8472d9">

## Data Sources:
1.	ECDC website: Confirmed cases, Mortality, Hospitalization, Testing numbers.
2.	Eurostat Data: Population by age.

# What is Azure Data Factory

![ADF](https://github.com/venkat2705/Covid19_Prediction-Reporting/assets/60357150/76e49d37-f240-4e85-8a03-fa628c954c11)

Azure Data Factory is a powerful integration, transformation, and Orchstration tool which is also serverless and fully managed service for all of your data at scale.
By using Azure Data Factory, organizations can create efficient and reliable data pipelines, enabling them to integrate and process data at scale for various data analytics, business intelligence, and machine learning scenarios. It empowers data engineers and data analysts to build robust data solutions without the need for managing underlying infrastructure which makes it an ideal choics for cloud based data integration and transformation tasks.

## Project Goals

####  Data Ingestion: 
We need to build a proper mechanism to ingest data from 2 different  sources ECDC website and Bolb storage into ADLS GEN2.

#### Data Warehousing and ETL: 
This is the most important step of our project. We always get the data in raw format, so we must transform this data into usable format by using required transformations in Azure Data Factory. For this we have used different services like Dataflows, HD insight, and Databricks.

#### Data lake: 
We get data from different sources so we need to have a centralized repo to store them. Here we are using ADLS Gen 2.

#### Reporting: 
We use PowerBI to create interactive and visually appealing reports and dashboards. It is a powerful business intelligence and data visualization tool developed by Microsoft.

## Prerequisites

[![Stay Motivated](https://img.shields.io/badge/Stay-Motivated-teal.svg?style=for-the-badge)](https://github.com/venkat2705) [![Think_Big](https://img.shields.io/badge/Think-Big-orange.svg?style=for-the-badge)](https://www.linkedin.com/in/venkata-ramana-a-/) ![Work Hard](https://img.shields.io/badge/Work-Hard-blue.svg?style=for-the-badge)

First you need to have the above mindset.
Additionally, Familiarity with the used Azure services and its UI should be a benefit. Little python and SQL coding skills is a plus. 

## Services that we are going to use in this project.

1. Azure Data Lake Stoage Gen 2 : It is a scalable and secure cloud-based storage service provided by Microsoft Azure. It is designed to store and manage big data in its native format.
2. Azure Data Factory : It is a cloud-based data integration service and it enables users to efficiently orchestrate and automate the movement and transformation of data between different data stores and systems.
3. Azure DataBricks : It is a cloud-based analytics platform developed in collaboration with Databricks. It offers a fast, collaborative, and scalable environment for big data analytics and machine learning.
4. Azure SQL database : Azure SQL Database is a fully managed and cloud-based relational database service provided by Microsoft Azure. It offers a scalable and high-performance solution for hosting and managing SQL Server databases in the cloud.
5. Azure Triggers : These are specifically Azure Functions Triggers, are event-driven mechanisms in the Azure cloud platform. They allow users to execute serverless functions in response to specific events or triggers like data changes.
6. Azure HD insight: With HDInsight, users can process, analyze, and gain insights from large volumes of data, enabling data-driven decision-making and advanced analytics.

## Solution Architecture

Here is the solution architecture of our project

<img width="1440" alt="Covid_19_Solution_Architecture" src="https://github.com/venkat2705/Covid19_Prediction-Reporting/assets/60357150/da28f2d6-e0fa-4df2-bbfa-b6282415fd9e">


## Lets look at the solution to know why we have used specific technology in the architecture.

1)	Integration and Orchestration: We have uses ADF as an orchestration and integration tool because it can connect to all the data connectors. Having that vast array of connectors makes it the best tool for expansion if the volume of data gets increased hugely.
2)	Transformation technologies: We have used 3 transformation technics they are Azure data flow, Azure HD insight, and Azure Databricks. Just to show how capable Azure Data Factory is. Data flow gives you code free transformation and is better for smaller tasks. It lacks in ability to develop complex transformations. Other 2 requires little coding. ADF acts as an orchestration tool when dealing with Databricks and HD insight.
3)	Storage Solution used: We used Azure Blob storage to store the population data. It is a solution to store large amount of text and binary data. We have used Azure Data Lake Storage Gen2 as our data lake here. It is recommended storage in azure because of its capability to handle petabytes of data and Hundreds of GBs of throughput.
4)	Azure SQL Database: Azure SQL database is used for Data Warehouse purposes. Azure Synapse analytics provides us with better features but due to the small size of our data it is recommended to use Azure SQL database.
5)	Reporting: Used PowerBI for reporting and dashboarding the transformed data.

## high level project flow
Lets look at the project flow at a high level because it is not possible to go into each and every detail here.

1. Ingest covid19 data from ECDC website and Azure blob storage through ADF which demonstrates the integration skills of ADF.
2. Now for data warehousing purposes we use Azure data lake Gen2. Currently we store raw data that is ingested.
3. Lets transform this raw data into processed. We are using 3 transformation technics they are Azure data flow, Azure HD insight, and Azure Databricks. Just to show how capable Azure Data Factory is.
4. Then we push all this processed data into our Data warehouse ADLS Gen2 for ML/DS teams.
5. Or we can do analytics on the processed data in Azure SQL Database and create reports and dashboards on the analyzed data via PowerBI.

There is a good amount of work to be done between each of these steps to make architecture work. For this you need to be familiar with ADF and the above mentioned Azure services.




