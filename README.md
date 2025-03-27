# Azure Data Engineering Project

This project demonstrates an end-to-end data engineering pipeline solution built on Microsoft Azure. Designed as part of a teaching initiative, it addresses a fictional business scenario to showcase best practices in data pipeline development, transformation, and visualization.

---

## 📌 Project Overview

The project solves a common business challenge—understanding customer demographics and their purchasing behavior. It involves extracting customer and sales data from an on-premises SQL Server database, transforming the data in Azure, and generating actionable insights through a Power BI dashboard.

The final dashboard highlights key performance indicators (KPIs) such as product sales by gender and category, with interactive filtering options by date, product category, and gender.

---

## 📊 Business Requirements

The business has identified a lack of visibility into how gender demographics affect product sales. Key requirements include:

- **Sales by Gender and Product Category**: Display total units sold, total revenue, and gender breakdown of customers.
- **Data Filtering**: Allow filtering by product category, gender, and date.
- **User-Friendly Interface**: Provide stakeholders with an intuitive and interactive dashboard for self-service analytics.

---

## 🧩 Solution Architecture

The solution is divided into the following stages:

### 1. Data Ingestion
- Extract customer and sales data from an **on-premises SQL Server** database.
- Load raw data into **Azure Data Lake Storage (ADLS)** using **Azure Data Factory (ADF)**.

### 2. Data Transformation
- Use **Azure Databricks** to clean, enrich, and transform data.
- Organize data into **Bronze** (raw), **Silver** (cleansed), and **Gold** (aggregated) layers for better manageability and performance.

### 3. Data Loading & Reporting
- Load transformed data into **Azure Synapse Analytics** for querying and analysis.
- Build an interactive **Power BI dashboard** to visualize KPIs and trends.

### 4. Automation & Monitoring
- Schedule daily pipeline runs using **ADF triggers**.
- Monitor pipeline performance and failures via **ADF and Synapse** monitoring features.

---

## 🛠️ Technology Stack

- **Azure Data Factory (ADF)** – Orchestration & data movement  
- **Azure Data Lake Storage (ADLS)** – Scalable storage for raw and processed data  
- **Azure Databricks** – Data transformation and processing  
- **Azure Synapse Analytics** – Data warehousing & analytical querying  
- **Power BI** – Data visualization and reporting  
- **Azure Key Vault** – Secure secret and credential management  
- **SQL Server (On-Premises)** – Source system for transactional data

---

## ⚙️ Setup Instructions

### Prerequisites

- An active Azure subscription  
- Access to an on-premises SQL Server instance  
- Basic familiarity with Azure services

### Step 1: Azure Environment Setup

- Create a **Resource Group**
- Provision necessary services:
  - Azure Data Factory
  - Azure Data Lake Storage with `bronze`, `silver`, and `gold` containers
  - Azure Databricks workspace
  - Azure Synapse Analytics workspace
  - Azure Key Vault

### Step 2: Data Ingestion

- Set up SQL Server and restore the **AdventureWorks** sample database.
- Create ADF pipelines to extract data from SQL Server to the **bronze** container in ADLS.

### Step 3: Data Transformation

- Mount ADLS in Databricks using service principal credentials.
- Use Databricks notebooks to clean and transform data from **bronze** to **silver**, and finally to **gold**.

### Step 4: Data Loading and Reporting

- Load the **gold** dataset into Synapse SQL Pool.
- Connect Power BI to Synapse and create visualizations as per business requirements.

### Step 5: Automation and Monitoring

- Schedule daily data pipeline execution in ADF.
- Set up monitoring dashboards and alerts for pipeline runs.

### Step 6: Security and Governance

- Implement **Role-Based Access Control (RBAC)** using Azure Entra ID (formerly Azure Active Directory).
- Use Key Vault to securely manage secrets and connection strings.

### Step 7: End-to-End Testing

- Insert new records into the source SQL Server.
- Run the entire pipeline and validate that updated data appears on the Power BI dashboard.

---

## ✅ Conclusion

This project provides a scalable and automated data pipeline solution using Azure's modern data platform. It enables real-time insights into customer demographics and product performance, empowering stakeholders to make informed decisions based on up-to-date analytics.

