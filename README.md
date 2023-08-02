# Covid19_Prediction-Reporting
We will transform and make reports on the ECDC covid19 data. Azure Data Factory is used the most in this project.

## Data Sources:
1.	ECDC website: Confirmed cases, Mortality, Hospitalization, Testing numbers.
2.	Eurostat Data: Population by age.

# What is Azure Data Factory

![ADF](https://github.com/venkat2705/Covid19_Prediction-Reporting/assets/60357150/0b9b8904-442d-412a-9947-249e864d000e)


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
We use PowerBI to create interactive and visually appealing reports and dashboards
It is a powerful business intelligence and data visualization tool developed by Microsoft.

## Prerequisites

[![Stay Motivated](https://img.shields.io/badge/Stay-Motivated-teal.svg?style=for-the-badge)](https://github.com/venkat2705) [![Think_Big](https://img.shields.io/badge/Think-Big-orange.svg?style=for-the-badge)](https://www.linkedin.com/in/venkata-ramana-a-/) ![Work Hard](https://img.shields.io/badge/Work-Hard-blue.svg?style=for-the-badge)

There isn't much you need to know to begin with this project but the above.

Additionally, Familiarity with Cloud (preferably on Azure) should be a benefit. Little python and SQL coding skills is a plus.

## Services that we are going to use in this project.

1. Azure Data Lake Stoage Gen 2 : It is a scalable and secure cloud-based storage service provided by Microsoft Azure. It is designed to store and manage big data in its native format.
2. Azure Data Factory : It is a cloud-based data integration service and it enables users to efficiently orchestrate and automate the movement and transformation of data between different data stores and systems.
3. Azure DataBricks : It is a cloud-based analytics platform developed in collaboration with Databricks. It offers a fast, collaborative, and scalable environment for big data analytics and machine learning.
4. Azure SQL database : Azure SQL Database is a fully managed and cloud-based relational database service provided by Microsoft Azure. It offers a scalable and high-performance solution for hosting and managing SQL Server databases in the cloud.
5. Azure Triggers : These are specifically Azure Functions Triggers, are event-driven mechanisms in the Azure cloud platform. They allow users to execute serverless functions in response to specific events or triggers like data changes.
6. Azure HD insight: With HDInsight, users can process, analyze, and gain insights from large volumes of data, enabling data-driven decision-making and advanced analytics.

## Solution Architecture

Here is the solution architecture of our project

<img width="1440" alt="Covid_19_Solution_Architecture" src="https://github.com/venkat2705/Covid19_Prediction-Reporting/assets/60357150/1c13e4bb-df7a-4d7b-bdde-852369340917">

## Lets look at the solution to know why we have used specific technology in the architecture.

1)	Integration and Orchestration: We have uses ADF as an orchestration and integration tool because it can connect to all the data connectors. Having that vast array of connectors makes it the best tool for expansion if the volume of data gets increased hugely.
2)	Transformation technologies: We have used 3 transformation technics they are Azure data flow, Azure HD insight, and Azure Databricks. Just to show how capable Azure Data Factory is. Data flow gives you code free transformation and is better for smaller tasks. It lacks in ability to develop complex transformations. Other 2 requires little coding. ADF acts as an orchestration tool when dealing with Databricks and HD insight.
3)	Storage Solution used: We used Azure Blob storage to store the population data. It is a solution to store large amount of text and binary data. We have used Azure Data Lake Storage Gen2 as our data lake here. It is recommended storage in azure because of its capability to handle petabytes of data and Hundreds of GBs of throughput.
4)	Azure SQL Database: Azure SQL database is used for Data Warehouse purposes. Azure Synapse analytics provides us with better features but due to the small size of our data it is recommended to use Azure SQL database.
5)	Reporting: Used PowerBI for reporting and dashboarding the transformed data.




