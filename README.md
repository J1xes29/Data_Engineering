# Data Engineering Project: Indonesia Hospital Data Pipeline 🏥📊

## 📌 Overview
This repository contains a complete end-to-end Data Engineering project (Group 16). The project demonstrates the Extraction, Transformation, and Loading (ETL) process of Indonesian hospital data using **Pentaho Data Integration (PDI)**, data warehousing via **SQL**, and data visualization using **Power BI**.

## 🗂️ Project Structure

The project files are organized as follows:

*   **`Hospital_Indonesia_datasets.csv`**: The raw dataset containing comprehensive information about various hospitals across Indonesia.
*   **`pentaho_transform (ktr & kjb)/`**: Contains Pentaho ETL scripts to process the data and build a dimensional model (Star Schema).
    *   `Jobppt.kjb`: The main Pentaho Job that orchestrates the entire ETL pipeline.
    *   `hospital_clean.ktr`: Transformation for initial data cleansing and standardization.
    *   `fact_dim_ppt.ktr`: Transformation for generating and loading the Fact table.
    *   `jenis_dimension.ktr`: Transformation for the Hospital Type (Jenis) dimension.
    *   `kelas_dim.ktr`: Transformation for the Hospital Class (Kelas) dimension.
    *   `location_dim.ktr`: Transformation for the Location (Region/City) dimension.
    *   `owner_dim.ktr`: Transformation for the Ownership (Pemilik) dimension.
*   **`SQL Scripts/`**: 
    *   `ppt_olap (2).sql`: SQL script for creating the OLAP (Online Analytical Processing) schema, including DDL for facts and dimensions.
    *   `hasil.sql`: SQL script containing final queries or exported results.
*   **`powerBIRevisi4.pbix`**: The final interactive Power BI dashboard for data analysis, reporting, and visualization.
*   **`Presentasi Data Engineering.pdf`**: The project presentation slides summarizing the methodology, architecture, and business insights.

## ⚙️ Architecture & Workflow

1.  **Extract**: Raw data is ingested from the provided CSV dataset.
2.  **Transform**: Data is cleansed, filtered, and structured into a Star Schema (Fact and Dimensions) using Pentaho Data Integration transformations.
3.  **Load**: The structured data is loaded into a relational database warehouse using the provided SQL OLAP scripts.
4.  **Visualize**: Power BI connects to the data warehouse to generate interactive dashboards, allowing stakeholders to explore hospital distributions, capacities, and ownership metrics.

## 🚀 Prerequisites

To run this project locally, you will need the following installed on your machine:
*   **Pentaho Data Integration (PDI / Kettle)**
*   **Relational Database** (e.g., MySQL, PostgreSQL, or SQL Server)
*   **Power BI Desktop** (to open and interact with the `.pbix` dashboard)

## 🛠️ How to Run the Pipeline

1.  **Database Setup**: 
    *   Create a new database in your SQL client.
    *   Execute `ppt_olap (2).sql` to create the necessary tables and schema.
2.  **ETL Execution**: 
    *   Open Pentaho Data Integration (Spoon).
    *   Open the main job file: `Jobppt.kjb`.
    *   Update the database connection settings in Pentaho to point to your local database credentials.
    *   Run the job. This will automatically execute the child `.ktr` transformations to clean the data and populate the dimension and fact tables.
3.  **Dashboarding**: 
    *   Open `powerBIRevisi4.pbix` in Power BI Desktop.
    *   Go to **Transform Data** > **Data Source Settings** and point it to your local database if necessary.
    *   Click **Refresh** to load the latest ETL processed data into the visuals.

## 👥 Authors
*   Marcellino Wilson Rusli
*   Jason Alexander Wijaya
