# **azuredatafactoryprojectarslan**

Azure Data Factory Airline Data Platform
## **Overview**
This project builds a scalable airline analytics platform in Azure using Data Factory, Data Lake, and Delta Lake. It follows a bronze-silver-gold architecture to ingest, transform, and analyze airline, flight, passenger, airport, and booking data from multiple sources.

## **Architecture**
### **Bronze Layer**: 
Raw data ingestion from APIs, SQL databases, on-premises sources.

### **Silver Layer**: 
Cleans, transforms, and models data for analytics.

### **Gold Layer**: 
Creates aggregated business views for insights.

## **Key Resources**
### **Linked Services**:
Connections to Azure Data Lake, Azure SQL Database, HTTP endpoints.

### **Datasets**: 
Defines entities (airline, flight, passenger, airport, booking) in multiple formats.

### **Delta Lake**:
Stores optimized, upsertable data in silver/gold layers.


## **Major Pipelines**

### **on_prem_ingestion and sql_db_to_datalake**:

Ingests data from on-premises files using integration runtime and cloud databases into the Data Lake
### **api_ingestion**:

Fetches airport dimension data from an external API

Loads it into Data Lake (JSON format) for further processing

### **SilverPipeline**:

Cleans and transforms airline, flight, passenger, airport, and booking data

Applies business rules and stores results in the silver layer as Delta tables

### **gold_pipeline**:

Joins and aggregates data to create top-5 airline analytics and business views

Outputs to the gold layer for reporting

### **parent_pipeline**:

Orchestrates overall flow: ingestion → transformation → business views

## **Dataflows**
### **transformationdataflow** (Silver Layer):

Performs cleaning, filtering (age, country, gender), type casting, column splitting.

Writes cleaned dimensions to Delta tables.

### **BussinessviewFlow** (Gold Layer):

Joins booking with airline info

Aggregates ticket cost by airline

Ranks top-5 airlines and formats results for insights

## **Technologies Used**
Azure Data Factory (pipelines, mapping dataflows)

Azure Data Lake Storage Gen2

Delta Lake (upsertable, versioned tables)

APIs, On-premises, SQL DB data sources

No-code data transformation & orchestration
Clone the repository.

Import pipelines, datasets, linked services, and dataflows into ADF.

Configure linked services with your credentials.

Trigger the parent pipeline and monitor results in your Data Lake.

Screenshots
<img width="1915" height="875" alt="image" src="https://github.com/user-attachments/assets/cb1d95ac-8e43-439c-88f3-cb5acce58c45" />
<img width="1532" height="820" alt="image" src="https://github.com/user-attachments/assets/4755280b-fa55-4ce6-a937-c74acd0d8b99" />
<img width="1877" height="905" alt="image" src="https://github.com/user-attachments/assets/64e26b62-c083-4589-b9b9-0deba646cea3" />
<img width="1906" height="931" alt="image" src="https://github.com/user-attachments/assets/635be8ad-98dd-4d66-8d83-e292ac17a5d6" />
<img width="1891" height="782" alt="image" src="https://github.com/user-attachments/assets/0f492a56-efd9-4934-8ddd-4f7c689e71a8" />
<img width="1898" height="567" alt="image" src="https://github.com/user-attachments/assets/aac9a12c-e350-4b88-98ea-eacb87f25261" />
<img width="1903" height="702" alt="image" src="https://github.com/user-attachments/assets/f0338a75-17b8-4f61-ba73-a78fc9909858" />
<img width="1893" height="737" alt="image" src="https://github.com/user-attachments/assets/c65a41e3-dc20-44bc-8b25-1f5e840918cb" />






