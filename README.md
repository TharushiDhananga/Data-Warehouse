# Data-Warehouse
A Data Warehouse project for integrating, transforming, and analyzing data from multiple sources using ETL pipelines, dimensional modeling, and SQL-based reporting.

Step 1 - Extract data from multiple sources 
The extraction process pulls data from different sources and stores it in a staging area 
before transformation. The sources include: 
• Relational Databases (SQL Server) 
• CSV Files 
• Text Files

Order of Data Extraction 
1. Extract Customer Data to Staging (Database source) 
2. Extract Store Data to Staging (Database source) 
3. Extract CurrencyExchange Data to Staging (Database source) 
4. Extract Product Data to Staging (Database source) 
5. Extract Order Data to Staging (CSV file) 
6. Extract OrderRows Data to Staging (TXT file) 
7. Extract CustomerAddress Data to Staging (CSV file)

![image](https://github.com/user-attachments/assets/61e3146f-4054-4a4b-ad54-57ea5f158f45)


Step 2: Transform data in the staging area 
Once data is extracted, it undergoes cleaning, transformation, and standardization in the staging 
area before being loaded into the data warehouse. 

01) Key Mapping & Relationship Handling: 
• Use Lookup Transformation to find matching records in dimension tables. 
• Generate Surrogate Keys for dimension tables where necessary.

02) Slowly Changing Dimensions (SCD) Management: 
• For Customer and Store data, SCD Type 2 is used to maintain historical changes by 
adding effective date columns. 
• For other dimensions, SCD Type 1 is used where only the latest data is retained.

03) Data cleansing: 
• There are some Null values in weight Unit Measure, Weight, close date and 
status columns in Product table and Store table. So, data cleansing is used for 
replace those null values.
Data cleansing for Product data and store data

    ![image](https://github.com/user-attachments/assets/13aec976-e37e-4de1-938d-107c4508939b)





