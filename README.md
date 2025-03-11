# eCommerce Transactions - Exploratory Data Analysis (EDA) 🚀  

## 📌 Project Overview  
This project performs **Exploratory Data Analysis (EDA)** on an **eCommerce Transactions dataset** using **MySQL and Python (Jupyter Notebook)**. The goal is to extract meaningful **business insights** and understand customer behavior, product performance, and revenue trends.

## 📂 Dataset Description  
The dataset consists of three CSV files:  

- **Customers.csv** → Customer details (ID, Name, Region, Signup Date)  
- **Products.csv** → Product details (ID, Name, Category, Price)  
- **Transactions.csv** → Sales transactions (ID, Customer, Product, Date, Quantity, Total Value, Price)  

## ⚙️ Tools & Technologies Used  
- **Database:** MySQL (SQL Queries for data extraction)  
- **Python Libraries:** Pandas, SQLAlchemy, Matplotlib, Seaborn  
- **Jupyter Notebook** (for running SQL queries and visualizing insights)  

## 📊 EDA Insights Extracted  
✅ **Customer Distribution by Region** → Identifies top-performing markets  
✅ **Monthly Revenue Trends** → Analyzes seasonal sales spikes  
✅ **Best-Selling Products** → Determines the most popular items  
✅ **High-Value Customers (LTV)** → Recognizes top spenders for loyalty programs  
✅ **Top Product Categories by Region** → Helps with localized marketing strategies  

## 🛠️ Steps to Run This Project  
### 1️⃣ **Setup MySQL & Import Data**  
Ensure MySQL is installed and create a new database. Then, import the dataset into MySQL.  
```sql
CREATE DATABASE eCommerceDB;
USE eCommerceDB;
```
### 2️⃣ **Connect MySQL to Jupyter Notebook**  
```bash
pip install pandas pymysql sqlalchemy matplotlib seaborn
```
Use your credentials
```bash
from sqlalchemy import create_engine
engine = create_engine("mysql+mysqlconnector://root:yourpassword@localhost:3306/eCommerceDB")
```
Load the CSV files into MySQL tables (Customers, Products, Transactions).
```sql
from sqlalchemy import text

with engine.connect() as conn:
    conn.execute(text("DROP TABLE IF EXISTS transactions;"))
    conn.execute(text("DROP TABLE IF EXISTS customers;"))
    conn.execute(text("DROP TABLE IF EXISTS products;"))

customersDf.to_sql(name='customers', con=engine, if_exists='replace', index=False)
productsDf.to_sql(name='products', con=engine, if_exists='replace', index=False)
transactionsDf.to_sql(name='transactions', con=engine, if_exists='replace', index=False)

print("Data inserted successfully!")
```
### 3️⃣ Run EDA Queries & Visualization

## 🤝 Contributing
Feel free to submit pull requests or raise issues to improve this analysis!

## 📜 License
This project is open-source and free to use
