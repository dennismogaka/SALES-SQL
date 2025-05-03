# SALES-SQL

## Table of Contents
1. [Project Overview](#project-overview)  
2. [Dataset Description](#dataset-description)  
3. [Project Objectives](#project-objectives)  
4. [Data Source](#data-source)  
5. [Project Structure](#project-structure)  
6. [Data Analysis](#data-analysis)  
7. [Key Findings](#key-findings)  
8. [Recommendations](#recommendations)
   
### PROJECT OVERVIEW
The primary goal of this project is to perform a comprehensive analysis of sales data using SQL to uncover trends, identify high performing product category, low performing product categories  and provide actionable insights to support strategic decision making.

### DATASET DESCRIPTION
The dataset contains structured data for sales transactions. It will be used to support reporting, analytics and decision making processes.

### The key components of the dataset include:
 •	Tables: organized collections of data.  
 
 •	Relationships: Defined using primary and foreign keys to maintain data integrity across tables.
 
 •	Data types: Each column has a defined data type. E.g INT, CHAR, VARCHAR, DATE to ensure consistency.
### PROJECT OBJECTIVES

#### 1.	Perform Exploratory Data Analysis
•	Perform basic Exploratory Data Analysis to understand the dataset:
Check for NULLS and missing data

 Check for duplicates
 
 Determine the total Revenue

 Determine the total customers

 Determine the total product categories
 
 Outlier check
 
#### 2.	Evaluate product performance

 Determine the best selling  product categories based on revenue generated.

 Determine underperforming product categories.
 
#### 3.	Business Analysis

 Use SQL to answer specific business questions and derive insights from the sales data.
 
#### 4.	Support strategic decision-making 

Provide insights that help the business with marketing efforts and pricing strategies.

### DATA SOURCE

The data used in this analysis was sourced from the business and database created and the values entered into the table.


### PROJECT STRUCTURE
#### 1.	DATABASE SET-UP

##### •	Database creation

The project starts by creating a database named SALESRECORD

 ##### •	Table creation
 
A table named RETAILSALES is created to store the sales data.
The table structure includes columns with Transaction_ID, sales_Date, Customer_ID, Age, Product_Category, Quantity_Sold and Revenue.
Data was then inserted into the table.

### DATA ANALYSIS
The following SQL queries were developed to answer specific business Questions:

1.	**Write a query to create a database SALESRECORD**
```sql
create database SALESRECORD;
```

2.	**write a query to create Table RETAILSALES**
   
```sql
CREATE table RETAILSALES (
TRANSACTION_ID CHAR(5) PRIMARY KEY,
SALES_DATE DATE,
CUSTOMER_ID CHAR(5),
GENDER VARCHAR(10),
AGE CHAR(3),
CATEGORY VARCHAR(25),
QUANTITY CHAR(10),
PRICE_PER_UNIT FLOAT,
TOTAL_SALES FLOAT
);
```

3.	**Write a query and use it to add data into the RETAILSALES table created.**
```sql
insert into RETAILSALES(
TRANSACTION_ID,
SALES_DATE,
CUSTOMER_ID,
GENDER,
AGE,
CATEGORY,
QUANTITY,
PRICE_PER_UNIT,
TOTAL_SALES)
VALUES ("T100", "2024/01/01", "123", "MALE", "55", "SPORTS", "9", "365", "3285"),
("T101", "2024/01/02", "133", "FEMALE", "33", "CLOTHING", "7", "381", "2667"),
("T102", "2024/01/03", "143", "FEMALE", "23", "FURNITURE", "4", "219", "876"),
("T103", "2024/01/04", "153", "FEMALE", "31", "CLOTHING", "5", "170", "850"),
("T104", "2024/01/05", "163", "MALE", "52", "SPORTS", "7", "211", "1477"),
("T105", "2024/01/06", "173", "FEMALE", "42", "HOME & KITCHEN", "10", "477", "4770"),
("T106", "2024/01/07", "183", "FEMALE", "60", "ELECTRONICS", "3", "225", "675"),
("T107", "2024/01/08", "193", "FEMALE", "23", "BEAUTY", "2", "192", "384"),
("T108", "2024/01/09", "203", "MALE", "63", "CLOTHING", "5", "478", "2390"),
("T109", "2024/01/10", "213", "MALE", "44", "CLOTHING", "8", "381", "3048"),
("T110", "2024/01/11", "223", "FEMALE", "22", "ELECTRONICS", "4", "216", "864"),
("T111", "2024/01/12", "233", "FEMALE", "38", "FURNITURE", "6", "398", "2388"),
("T112", "2024/02/01", "243", "FEMALE", "56", "CLOTHING", "1", "477", "477"),
("T113", "2024/02/02", "253", "FEMALE", "66", "CLOTHING", "2", "308", "616"),
("T114", "2024/02/03", "263", "FEMALE", "45", "CLOTHING", "5", "267", "1335"),
("T115", "2024/02/04", "273", "MALE", "46", "SPORTS", "9", "322", "2898"),
("T116", "2024/02/05", "283", "MALE", "58", "SPORTS", "7", "345", "2415"),
("T117", "2024/02/06", "293", "FEMALE", "21", "HOME & KITCHEN", "3", "233", "699"),
("T118", "2024/02/07", "303", "FEMALE", "59", "SPORTS", "6", "144", "864"),
("T119", "2024/02/08", "313", "MALE", "42", "SPORTS", "5", "430", "2150"),
("T120", "2024/02/09", "323", "FEMALE", "61", "BEAUTY", "6", "216", "1296"),
("T121", "2024/02/10", "333", "FEMALE", "19", "HOME & KITCHEN", "9", "400", "3600"),
("T122", "2024/02/11", "343", "MALE", "73", "ELECTRONICS", "2", "373", "746"),
("T123", "2024/02/12", "353", "MALE", "56", "CLOTHING", "4", "184", "736"),
("T124", "2024/03/01", "363", "MALE", "35", "CLOTHING", "3", "325", "975"),
("T125", "2024/03/02", "373", "MALE", "66", "CLOTHING", "7", "470", "3290"),
("T126", "2024/03/03", "383", "FEMALE", "57", "SPORTS", "11", "294", "3234"),
("T127", "2024/03/04", "393", "FEMALE", "26", "ELECTRONIS", "4", "83", "332"),
("T128", "2024/03/05", "403", "MALE", "40", "HOME & KITCHEN", "9", "258", "2322"),
("T130", "2024/03/06", "413", "FEMALE", "39", "CLOTHING", "8", "339", "2712"),
("T131", "2024/07/03", "123", "MALE", "55", "SPORTS", "9", "365", "3285"),
("T132", "2024/08/03", "133", "FEMALE", "33", "CLOTHING", "7", "381", "2667"),
("T133", "2024/09/03", "143", "FEMALE", "23", "FURNITURE", "4", "219", "876"),
("T134", "2024/10/04", "153", "FEMALE", "31", "CLOTHING", "5", "170", "850"),
("T135", "2024/11/05", "163", "MALE", "52", "SPORTS", "7", "211", "1477"),
("T136", "2024/12/06", "173", "FEMALE", "42", "HOME & KITCHEN", "10", "477", "4770"),
("T137", "2024/07/07", "183", "FEMALE", "60", "ELECTRONICS", "3", "225", "675"),
("T138", "2024/11/08", "193", "FEMALE", "23", "BEAUTY", "2", "192", "384"),
("T139", "2024/12/09", "203", "MALE", "63", "CLOTHING", "5", "478", "2390"),
("T140", "2024/06/10", "213", "MALE", "44", "CLOTHING", "8", "381", "3048"),
("T141", "2024/07/11", "223", "FEMALE", "22", "ELECTRONICS", "4", "216", "864"),
("T142", "2024/12/18", "233", "FEMALE", "38", "FURNITURE", "6", "398", "2388"),
("T143", "2024/02/01", "243", "FEMALE", "56", "CLOTHING", "1", "477", "477"),
("T144", "2024/02/21", "253", "FEMALE", "66", "CLOTHING", "2", "308", "616"),
("T145", "2024/03/22", "263", "FEMALE", "45", "CLOTHING", "5", "267", "1335"),
("T146", "2024/04/23", "273", "MALE", "46", "SPORTS", "9", "322", "2898"),
("T147", "2024/05/24", "283", "MALE", "58", "SPORTS", "7", "345", "2415"),
("T148", "2024/06/25", "293", "FEMALE", "21", "HOME & KITCHEN", "3", "233", "699"),
("T149", "2024/07/26", "303", "FEMALE", "59", "SPORTS", "6", "144", "864"),
("T150", "2024/08/27", "313", "MALE", "42", "SPORTS", "5", "430", "2150"),
("T151", "2024/09/28", "323", "FEMALE", "61", "BEAUTY", "6", "216", "1296"),
("T152", "2024/10/29", "333", "FEMALE", "19", "HOME & KITCHEN", "9", "400", "3600"),
("T153", "2024/11/30", "343", "MALE", "73", "ELECTRONICS", "2", "373", "746"),
("T154", "2024/12/30", "353", "MALE", "56", "CLOTHING", "4", "184", "736"),
("T155", "2025/01/01", "363", "MALE", "35", "CLOTHING", "3", "325", "975"),
("T156", "2025/01/02", "373", "MALE", "66", "CLOTHING", "7", "470", "3290"),
("T157", "2025/01/03", "383", "FEMALE", "57", "SPORTS", "11", "294", "3234"),
("T158", "2025/01/04", "393", "FEMALE", "26", "ELECTRONIS", "4", "83", "332"),
("T159", "2025/01/05", "403", "MALE", "40", "HOME & KITCHEN", "9", "258", "2322"),
("T160", "2025/01/06", "413", "FEMALE", "39", "CLOTHING", "8", "339", "2712");
```


4.	**write a query and use it to check if data entered is reflecting in the table**
```sql
SELECT * FROM RETAILSALES;
```
5.	**Write a query to determine the total number of records in the dataset**
```sql
SELECT count(*) FROM RETAILSALES;
```
6.	**Write a query to identify the unique categories in the dataset**
```sql
select distinct CATEGORY FROM RETAILSALES;
```
7.	**write a query and use it to find out how many categories  we have in the dataset.**
```sql
select count(distinct CATEGORY) FROM RETAILSALES;
```
8.	**Customer_Id 393 had mispelt name Electronis instead ELECTRONICS. Write a query and make changes to the name.**
```sql
UPDATE RETAILSALES
SET CATEGORY="ELECTRONICS"
WHERE CUSTOMER_ID="393";
```
9.	**Write a query to find out how many Unique Customers are in the dataset**
```sql
select  count(DISTINCT CUSTOMER_ID) FROM RETAILSALES;
```
10.	**write a query and use it to retrieve the total sales**
```sql
Select sum(TOTAL_SALES) FROM RETAILSALES;
```
11.	**write a Query to calculate TOTAL SALES Per  PRODUCT CATEGORY**
```sql
SELECT CATEGORY,
sum(TOTAL_SALES) as netsales
FROM RETAILSALES
group by CATEGORY
order by netsales desc;
```
12.	**write a query to determine which product category had highest sales**
```sql
SELECT CATEGORY,
sum(TOTAL_SALES) as netsales
FROM RETAILSALES
group by CATEGORY
order by netsales desc
limit 1;
```
13.	**write a query to determine which product category had lowest sales**
```sql
SELECT CATEGORY,
sum(TOTAL_SALES) as netsales
FROM RETAILSALES
group by CATEGORY
order by netsales asc
limit 1;
```
14.	**write a query to determine which 3 product categories performed well**
```sql
SELECT CATEGORY,
sum(TOTAL_SALES) as netsales
FROM RETAILSALES
group by CATEGORY
order by netsales desc
limit 3;
```
15.	**write a query to determine  which 3 product categories didn’t perform well**
```sql
SELECT CATEGORY,
sum(TOTAL_SALES) as netsales
FROM RETAILSALES
group by CATEGORY
order by netsales ASC
limit 3;
```
16.	**write an sql query to determine  total quantity**
```sql
select sum(QUANTITY) AS TOTAL_QUANTITY FROM RETAILSALES;
```

17.	**Write a query to determine the average sales**
```sql
select avg(TOTAL_SALES) AS AVERAGESALES FROM RETAILSALES;
```
### KEY FINDINGS
 1. **Revenue Overview**
    
**Total Revenue:** 
```SQL

select sum(TOTAL_SALES) AS NETSALES FROM RETAILSALES;

```

**Best Performing Product Category:** 
```SQL
SELECT CATEGORY,
sum(TOTAL_SALES) as netsales
FROM RETAILSALES
group by CATEGORY
order by netsales desc
limit 1;
```
**Lowest Selling product category:** 
```SQL
SELECT CATEGORY,
sum(TOTAL_SALES) as netsales
FROM RETAILSALES
group by CATEGORY
order by netsales asc
limit 1;
```

 2. **Top 3 Product categories by revenue.**
```sql
SELECT CATEGORY,
sum(TOTAL_SALES) as netsales
FROM RETAILSALES
group by CATEGORY
order by netsales desc
limit 3;
```

 3. **Top 3 product categories by quantity**
```sql
SELECT CATEGORY,
sum(QUANTITY) as totalquantity
FROM RETAILSALES
group by CATEGORY
order by totalquantity desc
limit 3;
```
 4. **Bottom 3 product categories by revenue**
```sql
SELECT CATEGORY,
sum(TOTAL_SALES) as netsales
FROM RETAILSALES
group by CATEGORY
order by netsales ASC
limit 3;
```
5. **Bottom 3 product categories by quantity**
```sql
SELECT CATEGORY,
sum(QUANTITY) as totalquantity
FROM RETAILSALES
group by CATEGORY
order by totalquantity asc
limit 3;
```
### RECOMMENDATIONS

•	Increase marketing focus on high performing product categories.

•	Analyze low-performing product categories and investigate promotional opportunities to improve on sales.

•	Target top customers with exclusive offers.
