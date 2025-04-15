INTRODUCTION
1.1 Background (Problem):
Modern e-commerce platforms face significant challenges managing and analyzing data from multiple heterogeneous sources such as transactional databases, NoSQL systems, and real-time user activity streams. Fecom Inc., e-commerce marketplace, encountered the need to integrate data from different sources—SQL Server, MongoDB, and user clickstreams—to derive meaningful insights for business decision-making and improve customer experience.
1.2 Purpose:
The primary goal of this project is to build a scalable and integrated data management solution that consolidates data from diverse sources into a centralized Data Warehouse (DWH) using SQL Server. The system supports reporting, analytics, and business intelligence (BI) via Power BI dashboards to empower decision-makers with real-time, actionable insights.

1.3 Previous Work Done (Competitor Analysis):
ss revealed the use of robust data pipelines, integrated recommendation systems, and strong data visualization tools. These platforms use real-time analytics (often powered by Kafka and Spark), and modern BI tools. Fecom Inc. aims to adopt similar architectural strategies at a feasible scale.

1.4 Customers' Analysis
The dataset includes 96097 unique customers from 27 countries and 337 cities. These customers show varying purchasing behaviors, repeat orders, and preferences across 71 product categories. Customer segmentation and satisfaction analysis can be performed using order patterns, reviews, and delivery metrics.

1.5 Scope
Integrate SQL Server, MongoDB, and clickstream data using SSIS and Kafka-Spark streaming
Transform and load data into a SQL Server-based DWH
Design Power BI dashboards for reporting on sales, customer behavior, product trends, and logistics
Enable CRM, marketing, and performance analysis

1.6 Stakeholders / Beneficiaries
Management: Strategic decision-making
Marketing Team: Targeted campaigns and segmentation
Sales Team: Tracking performance, top products
Operations: Monitoring delivery delays and logistics
Data Analysts: Deep dive into product and customer data
Customers: Improved personalization and service delivery

1.7 Business Model
Fecom Inc. operates as a commission-based e-commerce marketplace, connecting customers and sellers globally. The platform generates revenue through:
• Seller commissions per transaction
• Featured listings and advertisements
• Delivery service margins
• Premium customer subscription features

2. OBJECTIVES / LIST OF SERVICES (MEASURABLE)
• Integrate structured and unstructured data from SQL Server, MongoDB, and Kafka
• Enable real-time clickstream ingestion using Apache Kafka + Spark Streaming
• Develop a unified DWH using SQL Server
• Create Power BI dashboards showing:
  Review Analysis ( positive , negative ,neutral)
  Customer satisfaction (based on ratings and reviews)
  Top 5 Reviewed Categories
  Order Volume Over Time
  Customer Acquisition Trend
  Order Status Distribution
  total amount paid by each payment type
Ensure real-time or near real-time reporting with <5 min latency
• Improve data quality and consistency across sources

3. DESIGN OVERVIEW
3.1 System Architecture
   ![image](https://github.com/user-attachments/assets/06e344f0-8e48-4832-955f-fab198b631b2)
   Data Sources:
• SQL Server: Stores transactional data including sales, orders, and inventory.
• MongoDB: Contains semi-structured data such as product catalogs and user profiles.
• Kafka: Ingests clickstream events and other real-time data from web or app interactions.
  Streaming Layer:
• Apache Kafka acts as the message broker for streaming data.
• Apache Spark Streaming processes real-time events from Kafka and prepares it for storage or analysis.
  ETL/Integration Layer:
• SQL Server Integration Services (SSIS) is used for:

o Extracting and transforming batch data from SQL Server and MongoDB.
o Loading the processed data into the SQL Server Data Warehouse (DWH).

Data Warehouse (DWH):
  • SQL Server DWH stores the integrated, cleaned, and structured data used for analytics and reporting.
Business Intelligence Layer:
• Power BI connects to the DWH to visualize data, create reports, and build dashboards for business users.
Orchestration (Optional Enhancement):
• Apache Airflow (shown in the image) could be used to schedule, monitor, and orchestrate the ETL and streaming jobs efficiently.

3.2 Data Design (Entity Relationship Diagram)
![image](https://github.com/user-attachments/assets/0c73940f-9c58-4a80-9921-5f778a67842d)
• Core entities: Customers, Orders, Products, Sellers, Order_Items, Payments, Reviews

DWH:
![image](https://github.com/user-attachments/assets/496503cb-9d6c-41b5-a50a-f4da2dd01482)

4. IMPLEMENTATION
4.1 Tools & Technologies
• Data Sources: SQL Server, MongoDB, Apache Kafka
• Streaming: Apache Spark Structured Streaming
• ETL: SQL Server Integration Services (SSIS)
• Data Warehouse: SQL Server
• Visualization: Power BI
• Languages: SQL, Python
• Others: VS Code / SSMS

4.3 Steps of Installation
1.Install SQL Server and MongoDB
2.Set up Kafka and Spark (local or cloud)
3.Develop SSIS packages to move data from SQL Server & MongoDB to the DWH
4.Create Spark jobs for processing Kafka streaming click data
5.Build SQL Server Data Warehouse schema
6.Connect Power BI to the DWH
7.Design dashboards and reports
8.Schedule automated ETL jobs and streaming ingestion pipelines
