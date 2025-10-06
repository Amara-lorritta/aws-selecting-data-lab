
## Selecting Data from a Database
## **Overview**

This hands-on AWS lab demonstrates how to use SQL SELECT statements and database operators to query and filter data.
The lab focuses on working with a MySQL database hosted on Amazon RDS, accessed securely through an EC2 Command Host using AWS Systems Manager (Session Manager).

By completing this lab, I learned to retrieve, count, and order data using SQL queries.

## **Objectives & Learning Outcomes**

After completing this lab, I was able to:

Use the SELECT statement to query a database

Apply comparison operators (<, >, =, AND, WHERE, ORDER BY)

Use the COUNT() function to count rows or values

Retrieve specific columns using column aliases (AS)

Sort query results in ascending or descending order

## **Architecture**
<img width="500" height="500" alt="a0f7e8eb-b30f-4bfc-bb24-247fb365ec78" src="https://github.com/user-attachments/assets/4b77eae5-9f02-4540-b6e1-42f27e31e359" />

## **Architecture Summary:**

User (Lab Student) connects via AWS Management Console

Amazon EC2 Command Host serves as the MySQL client

Amazon RDS MySQL hosts the world database

Data is queried from the country table using the SELECT statement and operators like WHERE, AND, and ORDER BY

## **Commands and Steps** 
```bash 
# Step 1: Connect to the MySQL database
sudo su
cd /home/ec2-user/
mysql -u root --password='re:St@rt!9'

# Step 2: View existing databases
SHOW DATABASES;

# Step 3: Verify the world database exists
USE world;
SHOW TABLES;

# Step 4: Query all rows and columns from the country table
SELECT * FROM world.country;

# Step 5: Count the number of rows in the country table
SELECT COUNT(*) FROM world.country;

# Step 6: View the structure of the country table
SHOW COLUMNS FROM world.country;

# Step 7: Query specific columns from the country table
SELECT Name, Capital, Region, SurfaceArea, Population FROM world.country;

# Step 8: Use column alias for better readability
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population FROM world.country;

# Step 9: Order results by population in ascending order
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country 
ORDER BY Population;

# Step 10: Order results by population in descending order
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country 
ORDER BY Population DESC;

# Step 11: Use WHERE clause with comparison operator
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country 
WHERE Population > 50000000 
ORDER BY Population DESC;

# Step 12: Combine multiple conditions using AND
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country 
WHERE Population > 50000000 AND Population < 100000000 
ORDER BY Population DESC;

# Step 13: Challenge - Find countries in Southern Europe with population > 50M
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country 
WHERE Population > 50000000 AND Region = "Southern Europe";
```

## **Screenshots**

01_show_databases.png
<img width="1305" height="476" alt="Screenshot 2025-10-05 063633" src="https://github.com/user-attachments/assets/261e4864-44c3-426f-9783-95efda44e79b" />

02_select_all_rows.png
<img width="1897" height="419" alt="Screenshot 2025-10-05 064048" src="https://github.com/user-attachments/assets/d52b4dbb-2fac-476e-826d-9ef93af09ac5" />

03_count_rows.png
<img width="1279" height="149" alt="Screenshot 2025-10-05 064242" src="https://github.com/user-attachments/assets/9a20ee3a-7f18-4d2d-b399-36e712f23f46" />

04_order_by_population.png
<img width="1297" height="406" alt="Screenshot 2025-10-05 064733" src="https://github.com/user-attachments/assets/e896270c-8e4a-406a-adf6-8ecde7d5983c" />

05_where_condition.png
<img width="1554" height="191" alt="Screenshot 2025-10-05 065635" src="https://github.com/user-attachments/assets/e354ecae-d183-4996-884e-49963d539907" />


## **Tools Used**

Amazon EC2 (Command Host) – to access MySQL client

Amazon RDS (MySQL) – relational database hosting the world dataset

AWS Systems Manager (Session Manager) – for secure terminal access

MySQL Command Line Interface (CLI) – to execute SQL queries

## **Key Takeaways**

Practiced using SELECT and COUNT() to extract and analyze data

Learned how to filter and organize results using WHERE, AND, and ORDER BY

Gained experience using comparison operators (<, >, =) in real-world queries

Understood how data retrieval works in an AWS cloud-hosted MySQL environment

## **Author**

Amarachi Emeziem
Cloud Security & IT Support Specialist | AWS & Azure Certified

🌐 LinkedIn

 
