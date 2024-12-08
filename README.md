
## Overview

This script performs data analysis on a CSV file containing sales data. It uses Apache Spark for distributed data processing and visualization libraries like Matplotlib and Seaborn to generate insights. Key tasks include data cleaning, sales calculations, and data visualization.

---

## Prerequisites

### Libraries
Ensure you have the following Python libraries installed:

- `pyspark`
- `matplotlib`
- `seaborn`
- `pandas`

### File Requirements
The script expects a CSV file named `data-1.csv` to be present at `/FileStore/tables/`.

---

## Steps Performed

### 1. Load and Preview Data
- The script reads the CSV file into a Spark DataFrame with the following configurations:
  - Schema inference: Disabled
  - Header: Enabled
  - Delimiter: Comma `,`

### 2. Initialize Spark Session
A Spark session is created using `SparkSession.builder.getOrCreate()`.

### 3. Data Inspection
- Displays the schema and the first few rows of the DataFrame.
- Counts missing values.
- Identifies duplicates.

### 4. Data Transformation and Aggregation
- Computes **total sales amount** using `Quantity * UnitPrice`.
- Identifies the **top-selling items** based on total quantity.
- Aggregates **total sales by country**.
- Counts the **total number of unique customers**.

### 5. Visualizations
#### Generated using Matplotlib and Seaborn:
1. **Line Plots:**
   - Quantity vs. Description
   - Quantity vs. Unit Price
2. **Scatter Plots:**
   - Quantity vs. Description
   - Quantity vs. Unit Price

Each plot includes:
- Axis formatting
- Titles for clarity

---

## How to Use the Script

1. **Set the file path:**
   Update the `file_location` variable if the data file is located elsewhere.

2. **Run the script:**
   Execute the script in an environment with Spark and Python dependencies.

3. **Analyze the results:**
   Review the printed insights and generated visualizations to understand sales trends.

---

## Key Functions

### `quick_overview(df)`
Provides a quick summary of the data, including:
- First records
- Count of null values
- Duplicate entries
- Schema details

---

## Output

1. **Insights:**
   - Total sales amount
   - Top-selling items
   - Total sales by country
   - Unique customer count

2. **Visualizations:**
   - Line plots showing sales trends.
   - Scatter plots highlighting relationships between key metrics.

---

## Example Output

- **Total Sales Amount:**  
  E.g., `$123,456.78`
  
- **Top Selling Items:**  
  ```
  +----------+-------------+--------------+
  | StockCode| Description | TotalQuantity|
  +----------+-------------+--------------+
  |   10001  |   Item A    |      5000    |
  +----------+-------------+--------------+
  ```

- **Sales by Country:**  
  ```
  +---------+------------+
  | Country | TotalSales |
  +---------+------------+
  |   USA   |  45678.90  |
  +---------+------------+
  ```

---

## Notes
- Ensure the `data-1.csv` file is properly formatted, as schema inference is disabled.
- Update visualizations if required to focus on different dimensions of the data.

For further enhancements, feel free to modify the code to suit your analysis needs.
