# Data-Warehousing---Azure-Data-Engineering-Project
Azure data engineering project - Yellow Cab



# Project Overview
This Azure project involves the extraction, transformation, and loading (ETL) of data from an API source into Azure Data Lake Storage (ADLS) using Azure Data Factory (ADF). The data is processed through different layers known as Bronze, Silver, and Gold, each serving a specific purpose in data management and analytics. Finally, the processed data is loaded into Azure Synapse Analytics for further analysis and visualization using Power BI.

# Project Architecture

# Data Source

Yellow Taxi Trip Data 2017: A publicly available dataset from Kaggle, containing information about taxi trips taken in New York City during 2017, including details such as pickup and dropoff, trip distances, fares, timestamps, and other relevant attributes.
Data Loading with Azure Data Factory (ADF)

Extraction: ADF extracts data from the API source using built-in connectors or custom activities.
Loading: ADF pipelines facilitate loading the extracted data into Azure Data Lake Storage (ADLS) Gen2.
Orchestration: ADF orchestrates the entire data loading process, from extraction to loading, ensuring efficient and reliable data ingestion.

# Azure Data Lake Storage (ADLS) Gen2
Central Storage Repository: ADLS Gen2 is the central storage repository for all ingested data.

# Organizational Layers:

Bronze Layer: Raw data stored in its original form for traceability and lineage.
Silver Layer: Data undergoes cleansing, deduplication, and transformation, creating structured tables optimized for analytics.
Gold Layer: Final version of the data, optimized for analytics and reporting, including copies of fact and dimension tables from the Silver layer.
Audit Layer: A copy of the data from the Gold layer, ensuring data integrity and providing a backup for compliance.

# Transformations with Azure Databricks (PySpark)

Transformations: Performed in the Bronze, Silver, and Gold layers using PySpark for data processing, including deduplication, cleaning, and enrichment.

# Data Loading into Azure Synapse Analytics

Azure Synapse Analytics: A cloud-based analytics service for data warehousing and big data analytics, integrating SQL analytics and Spark analytics.
Loading Process: Processed data from the Gold layer is loaded into Azure Synapse Analytics for further analysis and reporting.

# Data Visualization with Power BI

Power BI: A business analytics tool used to create interactive dashboards and reports from data loaded into Azure Synapse Analytics, providing powerful visualization capabilities for insights and data-driven decisions.

------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Implementation Details

**Data Source:** Yellow Taxi Trip Data 2017
**Description:** A dataset containing information about taxi trips in New York City during 2017.
**Storage in GitHub**: The dataset is stored in GitHub for easy access and version control.

# Azure Data Factory (ADF)

**Data Integration Service:** ADF is used to create, schedule, and orchestrate data workflows for ingesting, transforming, and loading data from various sources to different destinations.

**Extracting Data from the API Source:** ADF extracts data from API sources using built-in connectors or custom activities, handling authentication and data retrieval.

**Loading Data into ADLS Gen2:** ADF pipelines manage the movement of data from the source to ADLS Gen2, ensuring efficient and reliable data ingestion.

**ADF Pipelines Orchestration:** Pipelines consist of activities representing tasks such as copying data, transforming data, executing stored procedures, or running custom scripts, arranged in a logical sequence to define the data flow and control execution order.

# Azure Data Lake Storage (ADLS) Gen2

**Scalable and Secure Storage Solution:** Combines the capabilities of Azure Blob Storage with a hierarchical file system and enhanced performance and security features.
**Central Storage Repository:** ADLS Gen2 serves as the central storage repository for all ingested data.

# Organizational Layers:

**Bronze Layer:** Initial landing area for raw data, stored in its original form for traceability and archival purposes.
**Silver Layer:** Processed and transformed data in a structured format, supporting analytical queries and reporting.
**Gold Layer:** Final version of the data optimized for analytics and reporting, providing high-quality, reliable data for decision-making.
**Audit Layer:** A copy of the data from the Gold layer, ensuring data integrity and compliance.

# Azure Databricks (Data Transformation)

**Unified Analytics Platform**: Built on Apache Spark, providing a collaborative workspace for data engineers, data scientists, and analysts.
**Transformations:** Performed using PySpark, modifying, cleaning, and enriching data to prepare it for downstream analytics and reporting.

# Data in Azure Synapse Analytics

**Data Warehouse:** A cloud-based analytics service for data warehousing and big data analytics, integrating various analytics services.
**Loading Process:** Involves moving data from the Gold layer of the data lake into Azure Synapse Analytics for further analysis and reporting.
**Data Integration:** Built-in capabilities allow seamless integration with various data sources and formats, with data ingestion facilitated by ADF, Azure Databricks, or other data integration tools and services.

# Data in Azure Synapse Analytics

**Data Warehouse:** A cloud-based analytics service for data warehousing and big data analytics, integrating various analytics services.
**Loading Process:** Involves moving data from the Gold layer of the data lake into Azure Synapse Analytics for further analysis and reporting.
**Data Integration:** Built-in capabilities allow seamless integration with various data sources and formats, with data ingestion facilitated by ADF, Azure Databricks, or other data integration tools and services.

## Data Model

The data model for this project is designed using a star schema, a common and efficient database structure for organizing data in data warehouses. In a star schema, data is organized into a central fact table surrounded by dimension tables. This arrangement allows for efficient querying and reporting.

![image](https://github.com/JoelNithishKumar/Data-Warehousing---Azure-Data-Engineering-Project/assets/62141525/002b22c2-da83-46c9-8980-890381f01e4f)


# Star Schema Overview

**Fact Table:**

The fact table contains the primary measurements or metrics that the business is interested in 
analyzing. In this case, the fact table appears to contain information about taxi trips, such as 
pickup and drop-off times, passenger count, trip distance, and various identifiers (e.g., 
RatecodeID, PULocationID, DOLocationID). The primary key of the fact table is typically a 
composite key consisting of foreign keys referencing the dimension tables.

**Dimension Tables:**

Dimension tables provide context and descriptive attributes for the data in the fact table. Each 
dimension table represents a specific aspect of the data and contains descriptive attributes related 
to that aspect.

**In this model:**

**Time Dimension Table:**
• Contains attributes related to date and time, such as pickup and drop-off dates and times.

**Location Dimension Table:**
• Contains attributes related to pickup and drop-off locations, identified by LocationIDs.

**Vendor Dimension Table:**
• Contains attributes related to the taxi vendors, identified by VendorID.

**Price Dimension Table:**
• Contains attributes related to pricing details of the trips, such as fare amount, payment 
type, tip amount, etc.



# Data Visualization with Power BI

![image](https://github.com/JoelNithishKumar/Data-Warehousing---Azure-Data-Engineering-Project/assets/62141525/de15ad7b-7177-4e73-86ca-188beaf07320)
