# 🚀 AWS Data Engineering Pipeline – Bronze–Silver–Gold Architecture - Data Modeling
End-to-end AWS Data Engineering project implementing Bronze–Silver–Gold architecture using Amazon S3, Kinesis, Glue, Databricks, and Redshift for automated data ingestion, transformation, and analytics.

## 📌 Overview
This project demonstrates the design and implementation of a **cloud-native data engineering pipeline** on **AWS**, following the **Medallion Architecture (Bronze–Silver–Gold)** using **Databricks** and AWS services.  
The pipeline automates the process of **data ingestion, transformation, and modeling** for daily e-commerce sales and order analytics.

---

## 🧱 Architecture

### 🔸 Bronze Layer (Raw Zone)
- Ingests data from multiple sources (transactional DBs, APIs, CSVs).
- Stores data **as-is** in **Amazon S3 (Raw Bucket)**.
- AWS Services:
  - Amazon **S3**
  - **Kinesis Data Firehose** (for streaming data)
  - **AWS Glue Crawler** (for schema discovery)

### 🔸 Silver Layer (Cleansed Zone)
- Cleans and enriches data, removing duplicates and applying transformations.
- Handles **incremental loads**.
- AWS Services:
  - **AWS Glue Jobs / Databricks Notebooks** for ETL
  - **S3 (Processed Zone)**
  - **Delta Lake** for versioning and updates

### 🔸 Gold Layer (Analytics Zone)
- Creates **business-ready data models** using a **Star Schema**.
- Contains **Dimension** and **Fact** tables:
  - Dimension: Customers, Products, Payments, Region  
  - Fact: Sales
- AWS Services:
  - **Databricks SQL / Delta Tables**
  - **Amazon Redshift / Athena / QuickSight** for analytics and reporting

---

## 🧩 Data Flow
Source (Default DB)
↓
Amazon S3 (Raw Data - Bronze)
↓
Databricks / Glue Transformations (Silver)
↓
Databricks SQL / Redshift (Gold)
↓
QuickSight / Power BI Dashboards




---

## 📊 Star Schema Data Model

- **Fact Table:** `fact_sales`
  - Contains numeric measures (sales amount, quantity, discount, etc.)
- **Dimension Tables:**  
  - `dim_customers`  
  - `dim_products`  
  - `dim_payments`  
  - `dim_region`

---

## 🧠 Key Features

✅ End-to-end AWS pipeline for ETL automation  
✅ Incremental data processing in the Silver Layer  
✅ Star Schema design in the Gold Layer for analytics  
✅ Integration with Databricks for transformation and Delta Lake for version control  
✅ Real-time ingestion support via AWS Kinesis  
✅ Visualization-ready data in Redshift / QuickSight  

---

## 🧰 Tech Stack

| Category | Tools / Services |
|-----------|------------------|
| Cloud Platform | **AWS** |
| Storage | **Amazon S3** |
| Data Processing | **Databricks**, **AWS Glue**, **PySpark** |
| Streaming | **AWS Kinesis** |
| Data Modeling | **Delta Lake**, **Amazon Redshift** |
| Visualization | **AWS QuickSight**, **Power BI** |
| Orchestration | **AWS Lambda**, **Glue Workflow**, **Step Functions** |
| Language | **Python**, **SQL** |

---

## 📁 Folder Structure

aws-data-engineering-pipeline/
│
├── README.md
│
├── 01_default_source/
│   ├── sample_data/
│   │   ├── customers.csv
│   │   ├── products.csv
│   │   ├── payments.csv
│   │   ├── sales.csv
│   │   └── regions.csv
│   └── README.md
│
├── 02_bronze_layer/
│   ├── bronze_ingestion.py
│   └── README.md
│
├── 03_silver_layer/
│   ├── silver_transformations.py
│   └── README.md
│
├── 04_gold_layer/
│   ├── gold_modeling.py
│   └── README.md
│
├── architecture/
│   ├── aws_pipeline_architecture.png   ← (You can add architecture diagram here)
│   └── datamodel_star_schema.png
│
└── notebooks/
    ├── bronze_to_silver_databricks.ipynb
    ├── silver_to_gold_databricks.ipynb
    └── validations_and_reporting.ipynb


---

## 🧪 Future Enhancements

- Add **Airflow orchestration** for better scheduling and monitoring  
- Integrate **AWS Glue Catalog** with **Athena** for serverless querying  
- Implement **real-time dashboards** via AWS QuickSight  
- Add **CI/CD** for pipeline deployment using **CodePipeline**

---

## 👨‍💻 Author

**Vijay Kumar Theegala**  
📍 Data Engineer | Cloud & Big Data Enthusiast  
🔗 [GitHub](https://github.com/vijaytheegala) | [LinkedIn](https://www.linkedin.com/in/vijay-kumar-theegala-69b7bb190)

---

## 🧾 License
This project is open-source under the [MIT License](LICENSE).

---

## 🌟 Star the Repo
If you found this project useful, please ⭐ the repo to show support!

---

## 🧱 Example Commands
```bash
# Clone the repository
git clone https://github.com/vijaytheegala/aws-data-engineering-pipeline.git

# Navigate to project directory
cd aws-data-engineering-pipeline

# Run Bronze Layer ingestion
python 02_bronze_layer/bronze_ingestion.py

# Run Silver Layer transformations
python 03_silver_layer/silver_transformations.py

# Run Gold Layer modeling
python 04_gold_layer/gold_modeling.py

