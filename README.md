# Superstore Sales Data Analysis

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on a Superstore sales dataset using Python.

The analysis focuses on understanding sales, profit, quantity, discounts, customer segments, product categories, regions, and delivery time. Python libraries such as **Pandas, NumPy, Matplotlib, and Seaborn** are used for data processing, analysis, and visualization.

## The dataset contains **10,194 records and 21 original columns**. A new `Delivery Days` column is also created during the analysis.

## 🎯 Objectives

The main objectives of this task are:

* Load the Superstore dataset.
* Understand the structure and characteristics of the data.
* Inspect the first few records.
* Check data types and dataset information.
* Generate descriptive statistics.
* Convert order and shipping dates into datetime format.
* Calculate delivery duration.
* Identify unique product categories.
* Check for missing values.
* Analyze sales by product category.
* Create visualizations to understand sales performance.
* Extract useful business insights from the dataset.

---

## 📊 Dataset

The dataset used in this project is:

```text
samplesuperstore.csv
```

The dataset contains information related to:

* Order ID
* Order Date
* Ship Date
* Ship Mode
* Customer ID
* Customer Name
* Segment
* Country/Region
* City
* State/Province
* Postal Code
* Region
* Product ID
* Category
* Sub-Category
* Product Name
* Sales
* Quantity
* Discount
* Profit

The original dataset contains **21 columns** and **10,194 rows**.

---

## 🛠️ Technologies Used

| Technology       | Purpose                       |
| ---------------- | ----------------------------- |
| Python           | Programming language          |
| Pandas           | Data loading and manipulation |
| NumPy            | Numerical operations          |
| Matplotlib       | Data visualization            |
| Seaborn          | Statistical visualization     |
| Google Colab     | Development environment       |
| Jupyter Notebook | Interactive analysis          |

---

## 📁 Project Structure

```text
Superstore-Sales-Analysis/
│
├── samplesuperstore.csv
├── Superstore_Sales_Analysis.ipynb
└── README.md
```

---

## 🔄 Analysis Workflow

The project follows these major steps:

```text
Load Dataset
     ↓
Understand Dataset
     ↓
Data Inspection
     ↓
Descriptive Statistics
     ↓
Date Conversion
     ↓
Feature Creation
     ↓
Missing Value Analysis
     ↓
Category Analysis
     ↓
Data Visualization
     ↓
Business Insights
```

---

## 1. Import Required Libraries

The following Python libraries are imported:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

These libraries are used for data manipulation, numerical analysis, and visualization.

---

## 2. Load the Dataset

The CSV dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/samplesuperstore.csv")
```

The first five rows are then displayed using:

```python
df.head()
```

The dataset contains fields related to orders, customers, products, sales, discounts, and profits.

---

## 3. Dataset Information

The `df.info()` function is used to understand:

* Number of records
* Number of columns
* Column names
* Data types
* Non-null values
* Memory usage

The dataset contains **10,194 entries and 21 columns** before feature engineering.

---

## 4. Descriptive Statistics

The `describe()` function is used to obtain statistical information about numerical columns.

```python
df.describe()
```

The numerical columns include:

* Row ID
* Sales
* Quantity
* Discount
* Profit

For example, the mean sales value is approximately **228.23**, while the mean profit is approximately **28.67**.

---

## 5. Date Conversion

The `Order Date` and `Ship Date` columns are converted into datetime format:

```python
df['Order Date'] = pd.to_datetime(
    df['Order Date'],
    format='mixed'
)

df['Ship Date'] = pd.to_datetime(
    df['Ship Date'],
    format='mixed'
)
```

This allows date-based calculations and analysis.

---

## 6. Feature Engineering

A new feature called `Delivery Days` is created.

```python
df['Delivery Days'] = (
    df['Ship Date'] - df['Order Date']
).dt.days
```

This calculates the number of days between the order date and shipping date.

After creating this feature, the dataset contains **22 columns**.

---

## 7. Product Category Analysis

The dataset contains three main product categories:

```text
Office Supplies
Furniture
Technology
```

This is identified using:

```python
df['Category'].unique()
```

The notebook output confirms these three categories.

---

## 8. Missing Value Analysis

Missing values are checked using:

```python
df.isnull().sum()
```

The analysis shows **0 missing values** for all columns, including the newly created `Delivery Days` column.

Therefore, no missing-value treatment is required for this dataset.

---

## 9. Sales by Category

Sales are grouped by product category:

```python
category_sales = (
    df.groupby('Category')['Sales'].sum()
)

category_sales
```

The resulting total sales are:

| Category        |  Total Sales |
| --------------- | -----------: |
| Furniture       | 754,747.7613 |
| Office Supplies | 731,893.3140 |
| Technology      | 839,893.2790 |

According to the analysis, **Technology has the highest total sales**, followed by Furniture and Office Supplies.

---

## 10. Sales Visualization

A bar chart is created to visualize sales by category:

```python
category_sales.plot(
    kind='bar',
    figsize=(8,5)
)

plt.title("Sales by Category")
plt.ylabel("Total Sales")
plt.show()
```

This visualization makes it easier to compare sales performance between the three product categories.

---

## 📈 Key Findings

Based on the analysis performed in the notebook:

1. The dataset contains **10,194 sales records**.
2. There are **21 original columns**.
3. Two date columns were converted to datetime format.
4. A new `Delivery Days` feature was created.
5. The dataset contains three product categories:

   * Furniture
   * Office Supplies
   * Technology
6. No missing values were identified.
7. **Technology** generated the highest total sales among the three categories.
8. Sales and profit show considerable variation across transactions, as reflected in the descriptive statistics.

---

## 💡 Business Insights

The analysis can help a business understand:

* Which product categories generate the most sales.
* How sales vary across different products and regions.
* The relationship between discounts and profitability.
* Customer segment performance.
* Shipping and delivery patterns.
* Products or categories that may require further investigation.

---

## ▶️ How to Run the Project

### Option 1: Google Colab

1. Open Google Colab.
2. Upload the `.ipynb` notebook.
3. Upload `samplesuperstore.csv`.
4. Make sure the CSV is available at:

```text
/content/samplesuperstore.csv
```

5. Run the notebook cells from top to bottom.

### Option 2: Jupyter Notebook

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

Then start Jupyter:

```bash
jupyter notebook
```

Open the notebook and ensure `samplesuperstore.csv` is available in the appropriate location.

---

## 📦 Requirements

```text
Python 3.x
Pandas
NumPy
Matplotlib
Seaborn
Jupyter Notebook / Google Colab
```

---

## 🚀 Future Improvements

The analysis can be extended by adding:

* Monthly and yearly sales trends
* Profit by category and sub-category
* Regional sales analysis
* Customer segment analysis
* Top and bottom performing products
* Discount vs. profit analysis
* Delivery-time analysis
* Correlation analysis
* Sales and profit dashboards using Power BI
* Interactive visualizations

---

## 📝 Conclusion

This project demonstrates how Python can be used to perform **Exploratory Data Analysis on retail sales data**.

The workflow includes data loading, data inspection, descriptive statistics, date transformation, feature engineering, missing-value analysis, category analysis, and visualization.

The analysis identifies **Technology as the category with the highest total sales** in the dataset and provides a foundation for further business and sales analysis.

---

## 👩‍💻 Author

**Periyanayagi**

Data Science / Data Analytics

---

## 📄 License

This project is intended for **educational and learning purposes**.
