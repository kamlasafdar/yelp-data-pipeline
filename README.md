# Yelp Dataset ETL

This repository contains an ETL (Extract, Transform, Load) pipeline for processing a subset of the Yelp Open Dataset. The project focuses on cleaning and transforming raw JSON data from Yelp and then loading the processed information into a MySQL relational database for structured analysis.

## 📌 Project Goal

The primary goal is to prepare raw Yelp dataset JSON files for structured querying and analysis. This involves data cleaning, transformation, and efficient loading into a relational database.

## ✅ Key Features

- **JSON Data Cleaning & Validation**  
  Corrects malformed JSON structures, handles missing/null values, and validates data integrity across business, checkin, review, tip, and user datasets.

- **Data Structuring & Standardization**  
  Extracts relevant fields, converts string-based lists (like categories and dates) into proper arrays, removes duplicates, and standardizes text fields (e.g., title-casing names).

- **CSV Export**  
  Converts cleaned JSON data into structured CSV files (`businesses.csv`, `categories.csv`, `checkins.csv`) for easy ingestion.

- **MySQL Database Loading**  
  Utilizes `pymysql` to connect to a MySQL database and load a subset of the cleaned business, category, and check-in data into respective tables using `INSERT IGNORE` to manage data integrity.

## 🗂️ Project Structure

<pre> ``` . ├── business_fixed.json # Cleaned and processed business data ├── checkin_fixed.json # Cleaned and processed check-in data ├── review_fixed.json # Cleaned and processed review data ├── tip_fixed.json # Cleaned and processed tip data ├── user_fixed.json # Cleaned and processed user data ├── extracted_business_data.json # Intermediate extracted business data ├── businesses.csv # CSV for core business information ├── categories.csv # CSV for business categories ├── checkins.csv # CSV for check-in records └── 21F-9132 kamla safdar.ipynb # Main Jupyter Notebook with ETL logic ``` </pre>


> **Note:** Original Yelp JSON files are assumed to be located at  
`/Users/macbookpro/Downloads/Yelp JSON/yelp_dataset/`  
Please ensure these paths are correct or updated in the notebook.

## ⚙️ Setup and Usage

### ✅ Prerequisites

- Python 3.x
- MySQL Database Server
- Yelp Open Dataset JSON files

### 🔧 Installation

Clone the repository:

```bash
git clone https://github.com/kamlasafdar/yelp-dataset-etl.git
cd yelp-dataset-etl

```


Install Python dependencies:
```bash

pip install pymysql pandas jupyter
```


🛠️ MySQL Database Setup
Create a database named YelpDB
Create the necessary tables (Businesses, Categories, Checkins)
Example CREATE TABLE statements can be found in the notebook.
Update your MySQL connection details (host, user, password, database) inside the notebook code.
🚀 Running the ETL Process
Launch the notebook:
```bash
jupyter notebook "Yelp-data-Proccessing.ipynb"
```

Run all cells sequentially to:

Clean the raw JSON
Export to CSV
Load data into your MySQL database







