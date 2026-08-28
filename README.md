# 📊 Online Education Student Engagement & Dropout Risk Analysis

## 📌 Project Overview

Online learning platforms generate a large amount of student interaction data. One important question is:

> **Can student engagement be used to understand academic performance, predict student success, and identify dropout risk?**

This project analyzes online learning activity using student engagement and academic performance data.

The analysis focuses particularly on the relationship between:

* Student online activity
* Number of clicks/interactions
* Academic scores
* Engagement level
* Performance level
* Pass/fail status
* Dropout/withdrawal risk
* Final academic outcome

The project uses **Python, Pandas, NumPy, and data analysis techniques** to explore patterns in student engagement and academic outcomes.

---

## 🎯 Objectives

The main objectives of this project are:

1. Analyze student engagement in an online learning environment.
2. Understand how online activity relates to academic performance.
3. Examine the relationship between `total_clicks` and student outcomes.
4. Compare pass rates across different engagement levels.
5. Identify students associated with higher dropout risk.
6. Analyze the distribution of final academic outcomes.
7. Generate meaningful insights from student interaction data.

---

## 📂 Dataset

The project uses the following dataset:

```text
online_education_dataset.csv
```

The dataset contains **32,593 student records** and includes demographic, academic, engagement, performance, risk, and outcome-related information.

### Important Features

| Feature             | Description                               |
| ------------------- | ----------------------------------------- |
| `id_student`        | Unique student identifier                 |
| `gender`            | Student gender                            |
| `region`            | Student geographical region               |
| `highest_education` | Highest education qualification           |
| `studied_credits`   | Number of credits studied                 |
| `imd_band`          | Socioeconomic/deprivation band            |
| `total_clicks`      | Total online learning interactions/clicks |
| `avg_score`         | Average student score                     |
| `engagement_level`  | Student engagement category               |
| `performance_level` | Student performance category              |
| `risk_level`        | Student dropout/risk category             |
| `pass_flag`         | Indicates whether the student passed      |
| `dropout_flag`      | Indicates whether the student dropped out |
| `final_result`      | Final academic outcome                    |

The notebook shows three engagement categories:

```text
High
Medium
Low
```

and four final-result categories:

```text
Pass
Withdrawn
Fail
Distinction
```

---

## 🛠️ Technologies Used

The project is implemented using Python and commonly used data-analysis libraries.

### Programming Language

* Python

### Libraries

* **NumPy** – Numerical computing
* **Pandas** – Data loading, manipulation, grouping, and analysis

## The notebook begins by importing NumPy and Pandas and loads the dataset using `pd.read_csv()`.

## 📁 Project Structure

A recommended project structure is:

```text
Online-Education-Engagement-Analysis/
│
├── online_education_dataset.csv
├── online_education_analysis.ipynb
├── README.md
│
└── outputs/
    ├── charts/
    └── analysis_results/
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd Online-Education-Engagement-Analysis
```

### 2. Install Required Libraries

```bash
pip install numpy pandas matplotlib seaborn
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Then open:

```text
online_education_analysis.ipynb
```

### 4. Load the Dataset

The notebook loads the dataset using:

```python
import pandas as pd

df = pd.read_csv("online_education_dataset.csv")

df.head()
```

---

# 🔍 Analysis Performed

## 1. Data Loading

The dataset is loaded into a Pandas DataFrame.

```python
df = pd.read_csv("online_education_dataset.csv")
```

The first few records are inspected using:

```python
df.head()
```

---

## 2. Final Result Analysis

The project examines the distribution of students according to their final academic result.

The notebook reports:

| Final Result | Number of Students |
| ------------ | -----------------: |
| Pass         |             12,361 |
| Withdrawn    |             10,156 |
| Fail         |              7,052 |
| Distinction  |              3,024 |

These results show that **withdrawal is a substantial outcome in the dataset**, making student retention an important aspect of the analysis.

---

## 3. Engagement-Level Analysis

Student engagement is divided into three levels:

```text
High
Medium
Low
```

The project compares the average `pass_flag` for each engagement category.

The notebook produces the following results:

| Engagement Level | Pass Rate |
| ---------------- | --------: |
| High             |    78.14% |
| Medium           |    57.15% |
| Low              |    19.92% |

These results indicate a strong relationship in this dataset between engagement level and passing outcome: students in the **High engagement** group have the highest observed pass rate, while students in the **Low engagement** group have the lowest.

---

## 4. Student Performance Analysis

The dataset contains an `avg_score` variable representing average academic score.

It also includes a derived categorical variable:

```text
performance_level
```

with categories such as:

```text
High
Medium
Low
```

This allows student academic performance to be examined alongside their online engagement.

---

## 5. Dropout Risk Analysis

The project also contains a:

```text
risk_level
```

feature.

Risk categories include:

```text
Low Risk
High Risk
Very High Risk
```

The `dropout_flag` feature is used to represent dropout status.

```text
dropout_flag = 0 → Not dropped out
dropout_flag = 1 → Dropped out
```

This allows student engagement and performance information to be examined in relation to dropout risk.

---

# 📈 Key Findings

Based on the executed notebook results:

### 1. Student outcomes are diverse

Students fall into four final-result categories:

* Pass
* Withdrawn
* Fail
* Distinction

The dataset contains **10,156 withdrawn students**, indicating that retention is a significant area of interest.

### 2. Engagement is strongly associated with passing

The observed pass rates increase substantially as engagement increases:

```text
Low Engagement     → 19.92%
Medium Engagement  → 57.15%
High Engagement    → 78.14%
```

### 3. Online activity provides useful information

The dataset includes `total_clicks` as a measure of online interaction. This enables analysis of how student activity relates to academic performance and retention.

### 4. Academic performance and engagement can be studied together

The dataset combines:

```text
Online Engagement
       ↓
Total Clicks
       ↓
Academic Score
       ↓
Performance Level
       ↓
Final Result
       ↓
Dropout Risk
```

This provides a useful framework for understanding student outcomes in online education.

---

# 💡 Business / Educational Insights

The analysis can help educational institutions understand students' learning behavior.

For example:

### Early Identification

Students showing low engagement could potentially be identified for additional academic support.

### Student Retention

High withdrawal numbers indicate the importance of understanding factors associated with student retention.

### Academic Support

Students with lower engagement and lower academic performance may benefit from targeted intervention.

### Data-Driven Education

Online interaction data can provide institutions with additional information for understanding student progress and outcomes.

> **Important:** The analysis identifies relationships in the available dataset. It does not by itself establish that low engagement causes dropout or poor academic performance.

---

# 📊 Example Analysis Workflow

```text
                 Dataset
                    │
                    ▼
             Data Loading
                    │
                    ▼
             Data Inspection
                    │
                    ▼
          Engagement Analysis
                    │
                    ▼
        Academic Performance
                    │
                    ▼
            Pass Analysis
                    │
                    ▼
           Dropout Analysis
                    │
                    ▼
          Final Result Analysis
                    │
                    ▼
             Key Insights
```

---

# 🔬 Sample Code

### Import Libraries

```python
import numpy as np
import pandas as pd
```

### Load Dataset

```python
df = pd.read_csv("online_education_dataset.csv")
```

### Display First Records

```python
df.head()
```

### Analyze Final Results

```python
df["final_result"].value_counts()
```

### Calculate Pass Rate by Engagement

```python
df.groupby("engagement_level")["pass_flag"].mean()
```

---

# 📌 Dataset Summary

The dataset contains:

```text
Rows: 32,593
Unique Students: 28,785
```

Important numerical variables include:

```text
studied_credits
total_clicks
avg_score
pass_flag
dropout_flag
```

Categorical variables include:

```text
gender
region
highest_education
imd_band
engagement_level
performance_level
risk_level
final_result
```

The notebook's dataset summary confirms these fields and their observed category counts.

---

# 🎓 Conclusion

This project demonstrates how online learning interaction data can be analyzed to understand student academic outcomes and retention.

The analysis shows a clear pattern in the dataset:

> **Higher student engagement is associated with a higher observed pass rate.**

High-engagement students have an observed pass rate of approximately **78.14%**, compared with approximately **19.92%** for low-engagement students.

At the same time, the dataset contains a considerable number of withdrawn students, highlighting the importance of understanding student retention in online education.

Overall, this project demonstrates the value of using **data analysis to identify patterns in student engagement, performance, success, and dropout risk**.

---

# 🔮 Future Improvements

The project can be extended by adding:

* Exploratory Data Analysis (EDA)
* Correlation analysis
* Additional visualizations
* Feature engineering
* Statistical analysis
* Student dropout prediction
* Machine learning classification models
* Model evaluation using accuracy, precision, recall, and F1-score
* Feature importance analysis
* Student risk prediction dashboard

These extensions would allow the project to move from descriptive analysis toward predictive student-success and dropout-risk modeling.

---

# 👩‍💻 Project Information

**Project Title:**
Online Education Student Engagement & Dropout Risk Analysis

**Domain:**
Education / Data Science

**Programming Language:**
Python

**Primary Libraries:**
NumPy, Pandas

**Dataset:**
Online Education Dataset

**Analysis Type:**
Student Engagement, Academic Performance & Retention Analysis

---

## ⭐ Project Highlights

```text
✔ 32,593 student records analyzed
✔ Student engagement analysis
✔ Academic performance analysis
✔ Pass-rate analysis
✔ Dropout-risk analysis
✔ Final-result analysis
✔ Data-driven educational insights
```

---

## 📜 License

This project is intended for educational and analytical purposes.

If the dataset is distributed under a separate license, the original dataset license and attribution requirements should be followed.

---

## 🙏 Acknowledgement

This project demonstrates the application of Python-based data analysis techniques to online education data and explores how student engagement can be related to academic success and retention.
