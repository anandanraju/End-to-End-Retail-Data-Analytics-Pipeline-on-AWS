## End-to-End-Retail-Data-Analytics-Pipeline-on-AWS
An end-to-end cloud-based data analytics solution that processes retail sales data using AWS serverless services. The pipeline automates data ingestion, validation, transformation, and visualization to deliver business insights through an interactive Power BI dashboard.

### Project Overview

This project demonstrates the implementation of a modern data analytics pipeline using AWS. Retail sales data in CSV format is uploaded to Amazon S3, automatically processed through AWS Lambda, transformed using AWS Glue, and stored in a curated data lake. The final dataset is visualized in Power BI to provide actionable business insights.

### Features

* Automated CSV file ingestion
* Event-driven processing with AWS Lambda
* Data validation and preprocessing
* Schema discovery using AWS Glue Crawler
* ETL transformation with AWS Glue
* Curated data storage in Amazon S3
* Interactive Power BI dashboard
* Fully serverless architecture
* Scalable and cost-effective data pipeline

### Architecture

                         User
                           │
                    Upload CSV File
                           │
                           ▼
                      Amazon S3 
                      (Raw Zone)
                           │
                  S3 Event Notification
                           │
                           ▼
                       AWS Lambda
                 (Validation & Cleaning)
                           │
                           ▼
                        Amazon S3 
                    (Processed Zone)
                           │
                           ▼
                    AWS Glue Crawler
                           │
                           ▼
                  AWS Glue Data Catalog
                           │
                           ▼
                   AWS Glue ETL Job
              (Transformation & Enrichment)
                           │
                           ▼
                 Amazon S3 (Curated Zone)
                           │
                           ▼
                    Power BI Dashboard

### 🛠️ AWS Services Used

| AWS Service           | Purpose                                       |
| --------------------- | --------------------------------------------- |
| Amazon S3             | Stores raw, processed, and curated datasets   |
| AWS Lambda            | Validates and preprocesses uploaded CSV files |
| AWS Glue Crawler      | Discovers schema and creates metadata         |
| AWS Glue Data Catalog | Stores table metadata                         |
| AWS Glue ETL          | Cleanses and transforms retail data           |
| IAM                   | Manages access permissions                    |
| CloudWatch            | Monitors logs and Lambda execution            |

### Tech Stack

* Python
* AWS Lambda
* Amazon S3
* AWS Glue
* AWS Glue Crawler
* AWS Glue Data Catalog
* IAM
* Amazon CloudWatch
* Power BI

### Project Structure
```
Retail-Data-Analytics-Pipeline/
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── final/
│
├── lambda/
│   ├── lambda_function.py
│
├── glue/
│   ├── crawler/
│   └── visual_etl_job.py
│
├── dashboard/
│   ├── RetailDashboard.pbix
│
├── assets/
│   ├── architecture/
│   └── screenshots/
│
├── README.md
└── LICENSE
```
### Workflow

1. User uploads a retail sales CSV file.
2. The file is stored in the **Amazon S3 Raw Zone**.
3. An S3 event notification triggers an **AWS Lambda** function.
4. Lambda validates, cleans, and preprocesses the data.
5. The cleaned dataset is saved to the **Processed S3 Zone**.
6. AWS Glue Crawler scans the processed data and updates the Glue Data Catalog.
7. AWS Glue ETL transforms and enriches the data.
8. The final curated dataset is stored in the **Curated S3 Zone**.
9. Power BI connects to the curated data to create interactive dashboards.

### Dashboard Insights

The Power BI dashboard provides key retail business metrics, including:

* Total Sales
* Total Profit
* Total Orders
* Sales by Category
* Sales by Region
* Monthly Sales Trend
* Top Performing Products
* Top Customers
* Profit Analysis
* Sales Distribution
* KPI Cards
* Interactive Filters and Slicers

### Learning Outcomes

* Designed a scalable serverless data analytics architecture.
* Automated data ingestion using Amazon S3 event notifications.
* Built Python-based preprocessing logic with AWS Lambda.
* Implemented schema discovery using AWS Glue Crawler.
* Performed ETL transformations using AWS Glue.
* Created a curated data lake for reporting.
* Developed interactive business dashboards using Power BI.
* Gained hands-on experience with AWS cloud analytics services.

### Deployment Steps

1. Create Amazon S3 buckets for **Raw**, **Processed**, and **Curated** data.
2. Configure an S3 Event Notification to trigger AWS Lambda.
3. Deploy the Lambda function for data validation and preprocessing.
4. Create and run an AWS Glue Crawler.
5. Configure the AWS Glue ETL Job.
6. Execute the ETL job to generate the curated dataset.
7. Connect Power BI to the curated S3 data and build the dashboard.

### Author

**Anandan Raju**

If you found this project useful, consider giving it a ⭐ on GitHub!
