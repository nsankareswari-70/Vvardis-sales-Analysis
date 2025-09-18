# Vvardis-sales-Analysis
## Project Objective:
Creating a recurring and ad hoc analysis in MySQL with 300 rows of sample data.

Create a database named Vvardis in Mysql workbench
```sql
create database vvardis;
use vvardis;
CREATE TABLE sales (
    sale_id INT AUTO_INCREMENT PRIMARY KEY,
    sale_date DATE,
    region VARCHAR(50),
    channel VARCHAR(50),
    product_name VARCHAR(100),
    units_sold INT,
    unit_price DECIMAL(10,2),
    customer_type VARCHAR(20)
);
```





