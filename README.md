# Capstone_24MBMA67
# Used Car Market Analytics with PySpark

### An MBA Capstone Project using a Production-Style Data Pipeline in Databricks

This repository contains the complete end-to-end capstone project for the MBA General program. The project leverages a comprehensive used car dataset to solve five key business problems through a robust data pipeline and advanced analytics, all implemented within the Databricks Lakehouse Platform.
## 🚀 Project Objective

The primary goal is to transform a raw, complex dataset on used cars into clean, structured, and actionable business intelligence. By building an automated data pipeline, this project demonstrates how to derive insights into market trends, price drivers, brand value, and vehicle efficiency.
## 📊 Five Use Cases Addressed

This project uses data analytics to answer five core questions about the used car market:

1.  **Market Demand Analysis:** Which car brands and fuel types are most prevalent in the market?
2.  **Price Analysis by Segment:** How do key features like transmission type affect a car's average resale value?
3.  **Brand Efficiency Analysis:** Which brands offer the best balance of engine power versus fuel efficiency (mileage)?
4.  **Feature Correlation Analysis:** What are the most influential factors that drive a used car's price?
5.  **Safety & High-Wear Analysis:** Which geographical locations have the highest concentration of older, high-mileage vehicles, indicating potential maintenance and safety hotspots?
## ⚙️ Methodology: The Medallion Data Pipeline
To ensure data quality, reliability, and governance, the project is built using the industry-standard **Medallion Architecture**.

*   **🥉 Bronze Layer:** Ingested the raw `used_cars_data` and cleaned column names for compatibility. An ingestion timestamp was added for traceability.
*   **🥈 Silver Layer:** Created a "single source of truth" by reading from the Bronze layer. This step involved crucial data cleaning, such as parsing text to extract numeric values for `Mileage`, `Engine`, and `Power`, handling malformed "null" strings, and filtering out bad data.
*   **🥇 Gold Layer:** Built five distinct, aggregated, business-ready tables directly from the Silver layer. Each Gold table is designed to power a specific visualization on the final dashboard, providing clear answers to our five use cases.
## ✨ Key Findings & Visualizations
### 1. Market Demand: Maruti and Hyundai Dominate
Analysis of over 6,000 listings shows that **Maruti** and **Hyundai** are by far the most dominant brands in the used car market, indicating high volume and brand trust.
### 2. Price Analysis: Automatic Commands a Premium
Cars with **Automatic** transmission have a significantly higher average resale price compared to their Manual counterparts, reflecting consumer preference for convenience.
### 3. Brand Efficiency: A Clear Trade-Off
A scatter plot of average power vs. average mileage reveals a clear efficiency trade-off. Luxury brands like **Porsche** and **Lamborghini** offer high power but low mileage, while mass-market brands like **Maruti** provide high mileage with lower power.
### 4. Key Price Drivers: Power is Paramount
Correlation analysis confirms that a car's **Power (bhp)** and **Engine size (CC)** are the strongest positive drivers of its resale price. Conversely, **Kilometers Driven** has the strongest negative impact on value.
### 5. High-Wear Hotspots: Identifying Regional Trends
The analysis identified cities like **Chennai** and **Pune** as having a higher concentration of older (pre-2010) or high-mileage (>100k kms) vehicles, which can inform regional-specific marketing for new cars or maintenance services.
## 🛠️ Technology Stack
*   **Platform:** Databricks Community Edition
*   **Core Engine:** Apache Spark (via PySpark)
*   **Data Storage & Architecture:** Delta Lake (Medallion Architecture)
*   **Libraries:** Spark SQL, Pandas
*   **Visualization:** Native Databricks Dashboards
## 🔧 How to Replicate
1.  **Setup:** Create a cluster in a Databricks workspace.
2.  **Upload Data:** Upload the `used_cars_data.csv` file and create a table named `used_cars_data` in the `workspace.default` schema.
3.  **Run Pipeline:** Import the `Data_Pipeline.ipynb` notebook and run the single pipeline cell. This will automatically generate all the Bronze, Silver, and Gold tables in your schema.
4.  **Visualize:** The Gold tables are now ready to be used as sources for a new Databricks Dashboard to replicate the visualizations shown above.
