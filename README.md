# Vvardis-sales-Analysis
## Project Objective:
Creating a Recurring and Ad hoc analysis in MySQL with 300 rows of sample data.

## Quick Overview on Recurring and Ad hoc analyis

Recurring analysis provides data at a set interval (like monthly sales reports) and uses a standard format to track ongoing metrics, while ad hoc analysis generates specific, one-time reports in response to immediate questions or unique events, offering flexible exploration beyond scheduled reports. Ad hoc analysis is more flexible and reactive, whereas recurring analysis is pre-planned and consistent. 
### Recurring analysis 
- Purpose: To monitor key performance indicators (KPIs) and track performance over time, providing a consistent view of the business. 
- Timing: Done on a regular, predetermined schedule, such as weekly, monthly, or quarterly. 
- Structure: Uses standardized templates and fixed parameters, resulting in predictable data sets and polished formatting. 
- Examples: A monthly financial report sent to a CFO, quarterly sales performance analysis, or a weekly operational metrics dashboard. 
### Ad hoc analysis 
- Purpose: To answer specific, immediate questions or investigate complex, unique issues that standard reports don't cover. 
- Timing: Created on-demand, in real-time, or as needed to address new situations. 
- Structure: Flexible and unplanned, allowing users to dive deep into data and explore trends without being limited by predefined metrics. 
- Examples: Analyzing sales for a new product promotion during a specific holiday, investigating employee performance in a particular department, or exploring anomalies in system performance. 
## Key differences summarized
- Flexibility: Ad hoc analysis is highly flexible; recurring analysis is static. 
- Timing: Ad hoc is reactive; recurring is proactive. 
- Structure: Ad hoc is specific and unplanned; recurring is standardized and scheduled. 
- Scope: Ad hoc analysis explores beyond routine reports to uncover hidden patterns, while recurring analysis focuses on established metrics. 

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
### Inserting 300 rows of sample data
``` sql
INSERT INTO sales (sale_date, region, channel, product_name, units_sold, unit_price, customer_type) VALUES
('2025-01-12', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 1, 60.0, 'Returning'),
('2025-03-09', 'US', 'Consumer', 'Whitening_Strips', 9, 45.0, 'New'),
('2025-02-21', 'Europe', 'Consumer', 'Toothpaste', 14, 5.5, 'Returning'),
('2025-03-31', 'US', 'Consumer', 'Professional_Whitening', 7, 150.0, 'Returning'),
('2025-01-22', 'Europe', 'Consumer', 'Professional_Whitening', 7, 150.0, 'Returning'),
('2025-01-09', 'US', 'Consumer', 'Whitening_Strips', 15, 45.0, 'Returning'),
('2025-02-06', 'US', 'Consumer', 'Toothpaste', 10, 5.5, 'New'),
('2025-02-03', 'US', 'Consumer', 'Professional_Whitening', 9, 150.0, 'Returning'),
('2025-03-17', 'US', 'Consumer', 'Caries_Treatment_Kit', 6, 120.0, 'Returning'),
('2025-02-24', 'Europe', 'Dental_Professional', 'Whitening_Strips', 4, 45.0, 'Returning'),
('2025-02-28', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 3, 60.0, 'Returning'),
('2025-02-26', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 7, 60.0, 'New'),
('2025-03-26', 'US', 'Consumer', 'Mouthwash', 7, 8.0, 'Returning'),
('2025-02-09', 'US', 'Consumer', 'Mouthwash', 2, 8.0, 'New'),
('2025-01-16', 'US', 'Dental_Professional', 'Professional_Whitening', 7, 150.0, 'New'),
('2025-03-03', 'US', 'Consumer', 'Caries_Treatment_Kit', 6, 120.0, 'Returning'),
('2025-02-28', 'US', 'Dental_Professional', 'Toothpaste', 4, 5.5, 'New'),
('2025-01-17', 'US', 'Dental_Professional', 'Mouthwash', 7, 8.0, 'New'),
('2025-02-04', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 10, 60.0, 'New'),
('2025-02-08', 'Europe', 'Consumer', 'Toothpaste', 2, 5.5, 'New'),
('2025-03-24', 'US', 'Consumer', 'Whitening_Strips', 12, 45.0, 'Returning'),
('2025-03-08', 'US', 'Dental_Professional', 'Whitening_Strips', 7, 45.0, 'New'),
('2025-02-28', 'US', 'Consumer', 'Caries_Treatment_Kit', 14, 120.0, 'New'),
('2025-03-24', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 6, 120.0, 'New'),
('2025-02-14', 'US', 'Dental_Professional', 'Professional_Whitening', 2, 150.0, 'Returning'),
('2025-01-30', 'Europe', 'Dental_Professional', 'Whitening_Strips', 8, 45.0, 'Returning'),
('2025-03-13', 'US', 'Consumer', 'Mouthwash', 6, 8.0, 'New'),
('2025-03-28', 'Europe', 'Consumer', 'Professional_Whitening', 8, 150.0, 'New'),
('2025-03-16', 'US', 'Consumer', 'Caries_Treatment_Kit', 1, 120.0, 'New'),
('2025-01-14', 'US', 'Consumer', 'Caries_Treatment_Kit', 8, 120.0, 'New'),
('2025-02-06', 'Europe', 'Dental_Professional', 'Mouthwash', 3, 8.0, 'New'),
('2025-03-16', 'US', 'Dental_Professional', 'Toothpaste', 1, 5.5, 'Returning'),
('2025-01-01', 'US', 'Consumer', 'Professional_Whitening', 14, 150.0, 'New'),
('2025-03-22', 'Europe', 'Consumer', 'Professional_Whitening', 13, 150.0, 'New'),
('2025-03-05', 'US', 'Consumer', 'Professional_Whitening', 8, 150.0, 'New'),
('2025-03-05', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 3, 60.0, 'Returning'),
('2025-02-02', 'US', 'Consumer', 'Enamel_Repair_Gel', 14, 60.0, 'New'),
('2025-01-15', 'US', 'Dental_Professional', 'Whitening_Strips', 2, 45.0, 'Returning'),
('2025-02-28', 'Europe', 'Dental_Professional', 'Toothpaste', 8, 5.5, 'New'),
('2025-01-13', 'US', 'Consumer', 'Whitening_Strips', 11, 45.0, 'Returning'),
('2025-02-15', 'US', 'Consumer', 'Caries_Treatment_Kit', 3, 120.0, 'Returning'),
('2025-02-16', 'US', 'Consumer', 'Mouthwash', 14, 8.0, 'New'),
('2025-03-14', 'US', 'Consumer', 'Professional_Whitening', 13, 150.0, 'Returning'),
('2025-03-10', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 5, 120.0, 'New'),
('2025-01-06', 'US', 'Consumer', 'Whitening_Strips', 12, 45.0, 'New'),
('2025-02-07', 'Europe', 'Consumer', 'Professional_Whitening', 1, 150.0, 'New'),
('2025-01-03', 'US', 'Consumer', 'Mouthwash', 4, 8.0, 'New'),
('2025-03-30', 'Europe', 'Consumer', 'Professional_Whitening', 14, 150.0, 'Returning'),
('2025-03-06', 'Europe', 'Consumer', 'Professional_Whitening', 1, 150.0, 'Returning'),
('2025-02-26', 'Europe', 'Dental_Professional', 'Caries_Treatment_Kit', 2, 120.0, 'New'),
('2025-02-14', 'Europe', 'Dental_Professional', 'Mouthwash', 5, 8.0, 'Returning'),
('2025-02-05', 'Europe', 'Consumer', 'Whitening_Strips', 2, 45.0, 'Returning'),
('2025-02-13', 'US', 'Consumer', 'Toothpaste', 12, 5.5, 'New'),
('2025-02-04', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 1, 120.0, 'Returning'),
('2025-03-14', 'Europe', 'Dental_Professional', 'Toothpaste', 4, 5.5, 'Returning'),
('2025-03-30', 'US', 'Consumer', 'Enamel_Repair_Gel', 3, 60.0, 'Returning'),
('2025-01-24', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 3, 60.0, 'Returning'),
('2025-02-21', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 7, 120.0, 'New'),
('2025-03-03', 'US', 'Consumer', 'Mouthwash', 3, 8.0, 'Returning'),
('2025-01-10', 'US', 'Consumer', 'Professional_Whitening', 5, 150.0, 'Returning'),
('2025-01-27', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 8, 120.0, 'New'),
('2025-01-04', 'US', 'Consumer', 'Mouthwash', 11, 8.0, 'New'),
('2025-03-28', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 4, 120.0, 'New'),
('2025-02-18', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 8, 120.0, 'New'),
('2025-01-17', 'Europe', 'Consumer', 'Mouthwash', 9, 8.0, 'Returning'),
('2025-02-20', 'US', 'Consumer', 'Professional_Whitening', 10, 150.0, 'New'),
('2025-01-13', 'US', 'Consumer', 'Toothpaste', 14, 5.5, 'New'),
('2025-01-10', 'Europe', 'Dental_Professional', 'Mouthwash', 6, 8.0, 'New'),
('2025-03-06', 'Europe', 'Dental_Professional', 'Caries_Treatment_Kit', 2, 120.0, 'New'),
('2025-03-19', 'US', 'Dental_Professional', 'Toothpaste', 8, 5.5, 'Returning'),
('2025-02-21', 'Europe', 'Consumer', 'Whitening_Strips', 2, 45.0, 'Returning'),
('2025-03-25', 'Europe', 'Dental_Professional', 'Professional_Whitening', 1, 150.0, 'New'),
('2025-01-07', 'Europe', 'Consumer', 'Mouthwash', 7, 8.0, 'Returning'),
('2025-02-13', 'US', 'Consumer', 'Caries_Treatment_Kit', 5, 120.0, 'Returning'),
('2025-03-10', 'Europe', 'Consumer', 'Toothpaste', 9, 5.5, 'Returning'),
('2025-02-14', 'Europe', 'Consumer', 'Toothpaste', 12, 5.5, 'New'),
('2025-02-15', 'US', 'Dental_Professional', 'Toothpaste', 6, 5.5, 'Returning'),
('2025-02-19', 'Europe', 'Consumer', 'Professional_Whitening', 7, 150.0, 'Returning'),
('2025-03-15', 'Europe', 'Dental_Professional', 'Whitening_Strips', 1, 45.0, 'New'),
('2025-03-18', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 10, 120.0, 'Returning'),
('2025-02-18', 'US', 'Consumer', 'Mouthwash', 12, 8.0, 'New'),
('2025-02-24', 'US', 'Dental_Professional', 'Toothpaste', 3, 5.5, 'New'),
('2025-02-18', 'US', 'Consumer', 'Mouthwash', 14, 8.0, 'New'),
('2025-01-14', 'US', 'Consumer', 'Mouthwash', 13, 8.0, 'Returning'),
('2025-02-06', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 4, 120.0, 'New'),
('2025-01-11', 'Europe', 'Dental_Professional', 'Whitening_Strips', 2, 45.0, 'New'),
('2025-02-02', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 5, 60.0, 'New'),
('2025-01-11', 'US', 'Consumer', 'Mouthwash', 7, 8.0, 'Returning'),
('2025-02-18', 'US', 'Dental_Professional', 'Mouthwash', 1, 8.0, 'Returning'),
('2025-02-23', 'US', 'Dental_Professional', 'Professional_Whitening', 4, 150.0, 'New'),
('2025-01-13', 'US', 'Dental_Professional', 'Toothpaste', 8, 5.5, 'Returning'),
('2025-01-18', 'Europe', 'Consumer', 'Professional_Whitening', 5, 150.0, 'New'),
('2025-01-31', 'US', 'Consumer', 'Toothpaste', 15, 5.5, 'Returning'),
('2025-01-30', 'Europe', 'Consumer', 'Toothpaste', 13, 5.5, 'Returning'),
('2025-03-10', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 6, 60.0, 'New'),
('2025-03-13', 'US', 'Dental_Professional', 'Whitening_Strips', 4, 45.0, 'Returning'),
('2025-03-03', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 13, 120.0, 'New'),
('2025-03-03', 'Europe', 'Consumer', 'Mouthwash', 13, 8.0, 'New'),
('2025-03-25', 'US', 'Dental_Professional', 'Professional_Whitening', 4, 150.0, 'New'),
('2025-03-23', 'Europe', 'Dental_Professional', 'Caries_Treatment_Kit', 5, 120.0, 'Returning'),
('2025-01-06', 'Europe', 'Consumer', 'Mouthwash', 8, 8.0, 'Returning'),
('2025-03-24', 'Europe', 'Dental_Professional', 'Caries_Treatment_Kit', 5, 120.0, 'New'),
('2025-02-02', 'US', 'Dental_Professional', 'Toothpaste', 2, 5.5, 'Returning'),
('2025-01-21', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 6, 60.0, 'Returning'),
('2025-03-22', 'US', 'Dental_Professional', 'Mouthwash', 6, 8.0, 'Returning'),
('2025-02-11', 'US', 'Dental_Professional', 'Toothpaste', 3, 5.5, 'Returning'),
('2025-03-08', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 6, 60.0, 'Returning'),
('2025-01-14', 'US', 'Consumer', 'Caries_Treatment_Kit', 14, 120.0, 'Returning'),
('2025-01-19', 'Europe', 'Dental_Professional', 'Professional_Whitening', 7, 150.0, 'New'),
('2025-03-30', 'US', 'Dental_Professional', 'Toothpaste', 4, 5.5, 'Returning'),
('2025-03-13', 'US', 'Consumer', 'Professional_Whitening', 6, 150.0, 'Returning'),
('2025-03-05', 'US', 'Dental_Professional', 'Whitening_Strips', 3, 45.0, 'Returning'),
('2025-02-17', 'Europe', 'Dental_Professional', 'Toothpaste', 8, 5.5, 'New'),
('2025-01-28', 'US', 'Dental_Professional', 'Professional_Whitening', 2, 150.0, 'New'),
('2025-01-31', 'US', 'Dental_Professional', 'Whitening_Strips', 6, 45.0, 'New'),
('2025-02-01', 'Europe', 'Dental_Professional', 'Whitening_Strips', 2, 45.0, 'Returning'),
('2025-01-24', 'Europe', 'Dental_Professional', 'Whitening_Strips', 2, 45.0, 'Returning'),
('2025-03-03', 'US', 'Consumer', 'Whitening_Strips', 15, 45.0, 'New'),
('2025-01-16', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 5, 60.0, 'New'),
('2025-01-24', 'US', 'Consumer', 'Caries_Treatment_Kit', 4, 120.0, 'New'),
('2025-03-16', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 5, 60.0, 'New'),
('2025-02-11', 'Europe', 'Consumer', 'Whitening_Strips', 10, 45.0, 'Returning'),
('2025-03-22', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 1, 60.0, 'New'),
('2025-02-16', 'Europe', 'Dental_Professional', 'Toothpaste', 5, 5.5, 'New'),
('2025-02-16', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 10, 120.0, 'Returning'),
('2025-01-17', 'Europe', 'Consumer', 'Professional_Whitening', 11, 150.0, 'Returning'),
('2025-02-06', 'Europe', 'Dental_Professional', 'Mouthwash', 5, 8.0, 'New'),
('2025-02-23', 'US', 'Dental_Professional', 'Toothpaste', 3, 5.5, 'New'),
('2025-03-21', 'Europe', 'Consumer', 'Mouthwash', 10, 8.0, 'New'),
('2025-03-04', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 14, 120.0, 'New'),
('2025-02-08', 'US', 'Consumer', 'Professional_Whitening', 8, 150.0, 'New'),
('2025-01-17', 'Europe', 'Consumer', 'Professional_Whitening', 10, 150.0, 'New'),
('2025-02-28', 'Europe', 'Dental_Professional', 'Professional_Whitening', 2, 150.0, 'New'),
('2025-02-04', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 4, 120.0, 'New'),
('2025-01-06', 'US', 'Consumer', 'Whitening_Strips', 15, 45.0, 'Returning'),
('2025-01-19', 'US', 'Consumer', 'Toothpaste', 1, 5.5, 'New'),
('2025-03-14', 'US', 'Dental_Professional', 'Mouthwash', 5, 8.0, 'Returning'),
('2025-01-10', 'US', 'Consumer', 'Whitening_Strips', 11, 45.0, 'Returning'),
('2025-03-26', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 7, 60.0, 'Returning'),
('2025-01-04', 'US', 'Consumer', 'Whitening_Strips', 3, 45.0, 'Returning'),
('2025-01-20', 'Europe', 'Consumer', 'Whitening_Strips', 4, 45.0, 'Returning'),
('2025-02-01', 'US', 'Dental_Professional', 'Toothpaste', 4, 5.5, 'Returning'),
('2025-03-04', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 8, 120.0, 'Returning'),
('2025-01-13', 'US', 'Dental_Professional', 'Professional_Whitening', 2, 150.0, 'New'),
('2025-01-15', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 3, 60.0, 'Returning'),
('2025-02-27', 'US', 'Consumer', 'Enamel_Repair_Gel', 3, 60.0, 'New'),
('2025-03-25', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 3, 60.0, 'Returning'),
('2025-01-04', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 4, 60.0, 'Returning'),
('2025-02-25', 'Europe', 'Consumer', 'Whitening_Strips', 8, 45.0, 'Returning'),
('2025-03-22', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 8, 120.0, 'Returning'),
('2025-02-11', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 5, 120.0, 'New'),
('2025-03-03', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 10, 120.0, 'Returning'),
('2025-03-16', 'Europe', 'Dental_Professional', 'Caries_Treatment_Kit', 2, 120.0, 'New'),
('2025-03-15', 'Europe', 'Dental_Professional', 'Mouthwash', 3, 8.0, 'New'),
('2025-03-13', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 8, 60.0, 'Returning'),
('2025-02-10', 'Europe', 'Dental_Professional', 'Mouthwash', 4, 8.0, 'New'),
('2025-02-05', 'Europe', 'Dental_Professional', 'Mouthwash', 3, 8.0, 'New'),
('2025-01-10', 'US', 'Consumer', 'Toothpaste', 2, 5.5, 'Returning'),
('2025-03-07', 'US', 'Consumer', 'Enamel_Repair_Gel', 9, 60.0, 'New'),
('2025-03-26', 'Europe', 'Consumer', 'Toothpaste', 13, 5.5, 'New'),
('2025-01-09', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 9, 120.0, 'Returning'),
('2025-01-21', 'Europe', 'Dental_Professional', 'Whitening_Strips', 7, 45.0, 'New'),
('2025-03-31', 'US', 'Dental_Professional', 'Toothpaste', 7, 5.5, 'New'),
('2025-03-06', 'US', 'Consumer', 'Professional_Whitening', 11, 150.0, 'New'),
('2025-01-18', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 3, 120.0, 'New'),
('2025-01-02', 'US', 'Consumer', 'Toothpaste', 1, 5.5, 'Returning'),
('2025-02-06', 'Europe', 'Dental_Professional', 'Mouthwash', 7, 8.0, 'Returning'),
('2025-02-27', 'US', 'Dental_Professional', 'Toothpaste', 2, 5.5, 'Returning'),
('2025-03-22', 'Europe', 'Consumer', 'Toothpaste', 10, 5.5, 'Returning'),
('2025-02-13', 'Europe', 'Consumer', 'Professional_Whitening', 2, 150.0, 'Returning'),
('2025-02-13', 'Europe', 'Consumer', 'Professional_Whitening', 3, 150.0, 'New'),
('2025-01-31', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 13, 120.0, 'Returning'),
('2025-01-07', 'US', 'Dental_Professional', 'Mouthwash', 4, 8.0, 'New'),
('2025-03-12', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 6, 60.0, 'Returning'),
('2025-01-21', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 10, 60.0, 'New'),
('2025-01-04', 'US', 'Consumer', 'Professional_Whitening', 2, 150.0, 'New'),
('2025-03-30', 'Europe', 'Dental_Professional', 'Toothpaste', 5, 5.5, 'New'),
('2025-02-17', 'Europe', 'Consumer', 'Toothpaste', 9, 5.5, 'New'),
('2025-01-30', 'Europe', 'Dental_Professional', 'Professional_Whitening', 3, 150.0, 'Returning'),
('2025-01-03', 'US', 'Dental_Professional', 'Mouthwash', 5, 8.0, 'New'),
('2025-02-24', 'Europe', 'Consumer', 'Mouthwash', 8, 8.0, 'Returning'),
('2025-03-13', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 9, 120.0, 'New'),
('2025-02-12', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 3, 60.0, 'Returning'),
('2025-03-06', 'Europe', 'Dental_Professional', 'Toothpaste', 3, 5.5, 'New'),
('2025-03-20', 'Europe', 'Consumer', 'Mouthwash', 11, 8.0, 'New'),
('2025-03-26', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 1, 120.0, 'New'),
('2025-02-18', 'US', 'Dental_Professional', 'Toothpaste', 1, 5.5, 'Returning'),
('2025-03-26', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 7, 60.0, 'New'),
('2025-02-08', 'Europe', 'Consumer', 'Professional_Whitening', 11, 150.0, 'New'),
('2025-02-28', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 14, 120.0, 'New'),
('2025-01-22', 'US', 'Consumer', 'Caries_Treatment_Kit', 1, 120.0, 'Returning'),
('2025-02-04', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 2, 120.0, 'New'),
('2025-01-22', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 8, 60.0, 'New'),
('2025-01-10', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 7, 120.0, 'New'),
('2025-01-20', 'US', 'Dental_Professional', 'Toothpaste', 4, 5.5, 'New'),
('2025-03-06', 'Europe', 'Dental_Professional', 'Professional_Whitening', 7, 150.0, 'Returning'),
('2025-02-04', 'US', 'Dental_Professional', 'Whitening_Strips', 4, 45.0, 'Returning'),
('2025-01-01', 'Europe', 'Consumer', 'Professional_Whitening', 2, 150.0, 'New'),
('2025-02-12', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 3, 60.0, 'Returning'),
('2025-01-12', 'US', 'Dental_Professional', 'Whitening_Strips', 1, 45.0, 'New'),
('2025-02-10', 'US', 'Consumer', 'Caries_Treatment_Kit', 6, 120.0, 'Returning'),
('2025-01-15', 'Europe', 'Dental_Professional', 'Professional_Whitening', 7, 150.0, 'Returning'),
('2025-01-18', 'US', 'Consumer', 'Toothpaste', 15, 5.5, 'New'),
('2025-01-02', 'US', 'Dental_Professional', 'Whitening_Strips', 4, 45.0, 'Returning'),
('2025-02-05', 'US', 'Consumer', 'Professional_Whitening', 13, 150.0, 'New'),
('2025-03-06', 'US', 'Dental_Professional', 'Mouthwash', 1, 8.0, 'New'),
('2025-02-08', 'US', 'Dental_Professional', 'Professional_Whitening', 2, 150.0, 'New'),
('2025-02-24', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 8, 120.0, 'New'),
('2025-01-01', 'Europe', 'Dental_Professional', 'Mouthwash', 1, 8.0, 'Returning'),
('2025-01-04', 'Europe', 'Consumer', 'Toothpaste', 12, 5.5, 'Returning'),
('2025-03-26', 'US', 'Dental_Professional', 'Whitening_Strips', 5, 45.0, 'New'),
('2025-01-22', 'Europe', 'Dental_Professional', 'Toothpaste', 8, 5.5, 'Returning'),
('2025-03-20', 'US', 'Dental_Professional', 'Mouthwash', 8, 8.0, 'Returning'),
('2025-02-18', 'US', 'Dental_Professional', 'Toothpaste', 7, 5.5, 'Returning'),
('2025-01-12', 'US', 'Consumer', 'Professional_Whitening', 13, 150.0, 'New'),
('2025-01-06', 'Europe', 'Dental_Professional', 'Whitening_Strips', 8, 45.0, 'New'),
('2025-03-25', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 1, 60.0, 'New'),
('2025-01-23', 'Europe', 'Dental_Professional', 'Toothpaste', 3, 5.5, 'New'),
('2025-02-02', 'US', 'Consumer', 'Whitening_Strips', 1, 45.0, 'New'),
('2025-01-23', 'US', 'Consumer', 'Mouthwash', 7, 8.0, 'Returning'),
('2025-01-18', 'Europe', 'Dental_Professional', 'Whitening_Strips', 7, 45.0, 'New'),
('2025-02-02', 'US', 'Consumer', 'Enamel_Repair_Gel', 13, 60.0, 'New'),
('2025-01-28', 'Europe', 'Consumer', 'Whitening_Strips', 14, 45.0, 'New'),
('2025-01-12', 'Europe', 'Consumer', 'Professional_Whitening', 11, 150.0, 'Returning'),
('2025-02-06', 'US', 'Dental_Professional', 'Professional_Whitening', 5, 150.0, 'New'),
('2025-03-18', 'Europe', 'Dental_Professional', 'Toothpaste', 8, 5.5, 'Returning'),
('2025-03-25', 'US', 'Consumer', 'Enamel_Repair_Gel', 13, 60.0, 'Returning'),
('2025-02-04', 'US', 'Dental_Professional', 'Professional_Whitening', 5, 150.0, 'New'),
('2025-02-22', 'Europe', 'Dental_Professional', 'Professional_Whitening', 5, 150.0, 'Returning'),
('2025-02-15', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 1, 60.0, 'Returning'),
('2025-03-01', 'US', 'Dental_Professional', 'Toothpaste', 7, 5.5, 'New'),
('2025-02-17', 'Europe', 'Consumer', 'Professional_Whitening', 11, 150.0, 'Returning'),
('2025-01-12', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 12, 60.0, 'Returning'),
('2025-03-08', 'US', 'Consumer', 'Mouthwash', 9, 8.0, 'Returning'),
('2025-01-15', 'US', 'Consumer', 'Caries_Treatment_Kit', 7, 120.0, 'New'),
('2025-03-07', 'Europe', 'Consumer', 'Mouthwash', 12, 8.0, 'Returning'),
('2025-03-30', 'Europe', 'Dental_Professional', 'Caries_Treatment_Kit', 5, 120.0, 'New'),
('2025-01-19', 'US', 'Consumer', 'Caries_Treatment_Kit', 13, 120.0, 'Returning'),
('2025-03-02', 'US', 'Consumer', 'Caries_Treatment_Kit', 1, 120.0, 'Returning'),
('2025-01-18', 'US', 'Consumer', 'Enamel_Repair_Gel', 11, 60.0, 'New'),
('2025-01-06', 'Europe', 'Consumer', 'Toothpaste', 13, 5.5, 'Returning'),
('2025-03-15', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 5, 60.0, 'New'),
('2025-03-12', 'Europe', 'Dental_Professional', 'Toothpaste', 5, 5.5, 'Returning'),
('2025-03-02', 'Europe', 'Consumer', 'Professional_Whitening', 11, 150.0, 'New'),
('2025-02-04', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 1, 120.0, 'Returning'),
('2025-03-04', 'US', 'Dental_Professional', 'Professional_Whitening', 8, 150.0, 'Returning'),
('2025-02-08', 'US', 'Dental_Professional', 'Toothpaste', 8, 5.5, 'Returning'),
('2025-03-20', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 12, 60.0, 'New'),
('2025-03-18', 'US', 'Consumer', 'Mouthwash', 13, 8.0, 'Returning'),
('2025-02-28', 'Europe', 'Consumer', 'Professional_Whitening', 9, 150.0, 'New'),
('2025-03-05', 'US', 'Dental_Professional', 'Professional_Whitening', 2, 150.0, 'New'),
('2025-03-11', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 14, 120.0, 'Returning'),
('2025-02-13', 'Europe', 'Dental_Professional', 'Toothpaste', 6, 5.5, 'Returning'),
('2025-03-03', 'US', 'Consumer', 'Whitening_Strips', 5, 45.0, 'New'),
('2025-02-26', 'Europe', 'Consumer', 'Professional_Whitening', 5, 150.0, 'New'),
('2025-03-11', 'Europe', 'Dental_Professional', 'Whitening_Strips', 4, 45.0, 'Returning'),
('2025-01-05', 'US', 'Consumer', 'Whitening_Strips', 10, 45.0, 'New'),
('2025-01-04', 'US', 'Consumer', 'Whitening_Strips', 13, 45.0, 'Returning'),
('2025-03-10', 'US', 'Dental_Professional', 'Enamel_Repair_Gel', 4, 60.0, 'Returning'),
('2025-02-08', 'US', 'Consumer', 'Mouthwash', 6, 8.0, 'Returning'),
('2025-01-09', 'US', 'Consumer', 'Professional_Whitening', 13, 150.0, 'Returning'),
('2025-01-22', 'US', 'Dental_Professional', 'Toothpaste', 5, 5.5, 'Returning'),
('2025-01-27', 'Europe', 'Consumer', 'Professional_Whitening', 6, 150.0, 'Returning'),
('2025-03-29', 'US', 'Dental_Professional', 'Toothpaste', 3, 5.5, 'Returning'),
('2025-03-08', 'Europe', 'Consumer', 'Mouthwash', 12, 8.0, 'Returning'),
('2025-02-21', 'US', 'Dental_Professional', 'Whitening_Strips', 7, 45.0, 'Returning'),
('2025-01-01', 'Europe', 'Dental_Professional', 'Enamel_Repair_Gel', 5, 60.0, 'New'),
('2025-01-09', 'Europe', 'Dental_Professional', 'Caries_Treatment_Kit', 4, 120.0, 'Returning'),
('2025-03-01', 'Europe', 'Dental_Professional', 'Professional_Whitening', 6, 150.0, 'Returning'),
('2025-01-06', 'US', 'Dental_Professional', 'Toothpaste', 8, 5.5, 'New'),
('2025-01-20', 'US', 'Consumer', 'Enamel_Repair_Gel', 15, 60.0, 'Returning'),
('2025-01-11', 'Europe', 'Consumer', 'Mouthwash', 3, 8.0, 'New'),
('2025-03-12', 'Europe', 'Consumer', 'Whitening_Strips', 12, 45.0, 'Returning'),
('2025-01-20', 'US', 'Consumer', 'Toothpaste', 4, 5.5, 'New'),
('2025-03-22', 'US', 'Consumer', 'Caries_Treatment_Kit', 11, 120.0, 'Returning'),
('2025-03-09', 'Europe', 'Consumer', 'Toothpaste', 2, 5.5, 'Returning'),
('2025-03-06', 'Europe', 'Consumer', 'Professional_Whitening', 2, 150.0, 'Returning'),
('2025-02-20', 'US', 'Dental_Professional', 'Caries_Treatment_Kit', 5, 120.0, 'New'),
('2025-01-29', 'US', 'Consumer', 'Enamel_Repair_Gel', 4, 60.0, 'New'),
('2025-03-14', 'US', 'Dental_Professional', 'Whitening_Strips', 7, 45.0, 'Returning'),
('2025-02-26', 'US', 'Dental_Professional', 'Mouthwash', 3, 8.0, 'Returning'),
('2025-01-25', 'Europe', 'Consumer', 'Toothpaste', 15, 5.5, 'Returning'),
('2025-03-23', 'US', 'Dental_Professional', 'Whitening_Strips', 1, 45.0, 'New'),
('2025-03-09', 'US', 'Consumer', 'Professional_Whitening', 4, 150.0, 'New'),
('2025-02-14', 'US', 'Dental_Professional', 'Mouthwash', 7, 8.0, 'Returning'),
('2025-01-16', 'Europe', 'Dental_Professional', 'Caries_Treatment_Kit', 5, 120.0, 'Returning'),
('2025-03-14', 'Europe', 'Consumer', 'Whitening_Strips', 15, 45.0, 'New'),
('2025-03-11', 'Europe', 'Dental_Professional', 'Mouthwash', 2, 8.0, 'New'),
('2025-02-28', 'US', 'Consumer', 'Caries_Treatment_Kit', 8, 120.0, 'New'),
('2025-02-26', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 11, 60.0, 'Returning'),
('2025-01-16', 'Europe', 'Dental_Professional', 'Caries_Treatment_Kit', 5, 120.0, 'Returning'),
('2025-02-11', 'US', 'Dental_Professional', 'Mouthwash', 6, 8.0, 'New'),
('2025-02-07', 'Europe', 'Dental_Professional', 'Professional_Whitening', 8, 150.0, 'Returning'),
('2025-03-12', 'Europe', 'Dental_Professional', 'Whitening_Strips', 8, 45.0, 'Returning'),
('2025-03-02', 'Europe', 'Consumer', 'Caries_Treatment_Kit', 1, 120.0, 'Returning'),
('2025-02-17', 'US', 'Dental_Professional', 'Toothpaste', 2, 5.5, 'Returning'),
('2025-01-09', 'US', 'Consumer', 'Mouthwash', 4, 8.0, 'Returning'),
('2025-03-12', 'US', 'Consumer', 'Toothpaste', 7, 5.5, 'Returning'),
('2025-02-25', 'Europe', 'Consumer', 'Enamel_Repair_Gel', 9, 60.0, 'New'),
('2025-03-11', 'Europe', 'Dental_Professional', 'Mouthwash', 1, 8.0, 'Returning');
```

``` sql
-- inserting 2 more rows for the year 2024
insert into sales(sale_date,region,channel,product_name,units_sold,unit_price,customer_type)
values('2024-07-13','Europe','Consumer','Toothpaste',3,6.5,'New'),
('2024-08-16','US','Dental_Professional','Whitening_Strips',3,45.0,'Returning');
```

### Recurring Analysis Queries

1. Monthly Revenue Trends

``` sql
select date_format(sale_date,'%Y') as year,date_format(sale_date,'%Y - %m') as month,
sum(units_sold*unit_price) as Revenue from sales
group by year,month 
order by year,month;
```
![img alt](https://github.com/nsankareswari-70/Vvardis-sales-Analysis/blob/e5b24337719ec229ee451e396cf4e483e33199c3/vvar2.png)

2. Monthly Revenue From US
``` sql
  select region as Region,date_format(sale_date,'%Y') as Year,date_format(sale_date,'%Y - %m') as Month,
sum(units_sold*unit_price) as Revenue from sales 
where region='US'
group by Year,Month 
order by Year,Month;
```
![img alt](https://github.com/nsankareswari-70/Vvardis-sales-Analysis/blob/1a47f2b39277375bd10dd2d39e6977aeacf0b1e5/vvar3.png)

3. Monthly Revenue From Europe
   ``` sql
    select region as Region,date_format(sale_date,'%Y') as Year,date_format(sale_date,'%Y - %m') as       Month,
        sum(units_sold*unit_price) as Revenue from sales 
       where region='Europe'
    group by Year,Month 
    order by Year,Month;
4. To Find the yearly revenue of the company
   ``` sql
          select date_format(sale_date,'%Y') as Year,
            sum(units_sold*unit_price) as Revenue from sales 
       group by Year;
   ```
![img alt](https://github.com/nsankareswari-70/Vvardis-sales-Analysis/blob/f6cc4a663ac94840c4ffcea2603a7ede7a4ff592/vvar4.png)  
5. Finding Revenue for a given date   
``` sql
select sale_date,
sum(units_sold*unit_price) as Revenue from sales where sale_date='2025-01-20'
group by sale_date;
```
6. Finding the most and least revenue-producing products each year
   ``` sql
   select date_format(sale_date,'%Y')as Year,product_name,
   sum(units_sold*unit_price) as Revenue from sales 
   group by product_name,Year order by Revenue desc;
```![img alt](https://github.com/nsankareswari-70/Vvardis-sales-Analysis/blob/ae333a68c58ca94284fcbbeb8514594b9b7a4be9/vvar5.png)
