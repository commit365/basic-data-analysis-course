# Lesson 18: Final Project - Data Analysis Case Study

## Objectives
By the end of this lesson, you will be able to:
- Apply the skills learned throughout the course to analyze a real-world dataset.
- Present your findings using visualizations created in Excel and Pandas.

## 1. Project Overview

In this final project, you will analyze a dataset of your choice. The goal is to apply the data analysis techniques you have learned, including data cleaning, exploratory data analysis (EDA), statistical analysis, and visualization, to derive meaningful insights. 

### 1.1 Selecting a Dataset

Choose a dataset that interests you. You can find datasets from various sources, including:

- [Kaggle](https://www.kaggle.com/datasets)
- [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php)
- [Government Open Data Portals](https://www.data.gov/)
- [Google Dataset Search](https://datasetsearch.research.google.com/)

### 1.2 Example Dataset

For demonstration purposes, let’s assume you choose a dataset on **Employee Salaries** with the following columns:

- `EmployeeID`
- `Name`
- `Department`
- `Age`
- `Salary`
- `Years of Experience`

## 2. Data Analysis Steps

### 2.1 Data Cleaning

1. **Load the Dataset**:
   - If using Excel, import the dataset directly. If using Pandas, load the dataset with:
   ```python
   import pandas as pd

   df = pd.read_csv('employee_salaries.csv')
   ```

2. **Inspect the Data**:
   - Check for missing values, duplicates, and data types.
   ```python
   print(df.info())
   print(df.isnull().sum())
   ```

3. **Clean the Data**:
   - Remove duplicates, fill or drop missing values, and correct data types if needed.
   ```python
   df.drop_duplicates(inplace=True)
   df['Salary'].fillna(df['Salary'].mean(), inplace=True)  # Example of filling missing values
   ```

### 2.2 Exploratory Data Analysis (EDA)

1. **Summary Statistics**:
   - Use descriptive statistics to summarize the data.
   ```python
   print(df.describe())
   ```

2. **Visualize Distributions**:
   - Create histograms for numerical columns (e.g., Age, Salary).
   ```python
   import matplotlib.pyplot as plt
   import seaborn as sns

   plt.figure(figsize=(10, 6))
   sns.histplot(df['Salary'], bins=20, kde=True)
   plt.title('Salary Distribution')
   plt.xlabel('Salary')
   plt.ylabel('Frequency')
   plt.show()
   ```

3. **Analyze Relationships**:
   - Use scatter plots to explore relationships between variables (e.g., Salary vs. Years of Experience).
   ```python
   plt.figure(figsize=(10, 6))
   sns.scatterplot(x='Years of Experience', y='Salary', data=df)
   plt.title('Salary vs. Years of Experience')
   plt.xlabel('Years of Experience')
   plt.ylabel('Salary')
   plt.show()
   ```

### 2.3 Statistical Analysis

1. **Calculate Mean, Median, and Mode**:
   - Calculate these statistics for Salary and Age.
   ```python
   mean_salary = df['Salary'].mean()
   median_salary = df['Salary'].median()
   mode_salary = df['Salary'].mode()[0]

   print(f'Mean Salary: {mean_salary}, Median Salary: {median_salary}, Mode Salary: {mode_salary}')
   ```

2. **Group Data**:
   - Group by Department and calculate average salary.
   ```python
   avg_salary_by_dept = df.groupby('Department')['Salary'].mean()
   print(avg_salary_by_dept)
   ```

### 2.4 Creating a Dashboard (Optional)

1. **Create PivotTables**:
   - Use PivotTables to summarize data interactively in Excel.

2. **Visualizations**:
   - Create charts to visualize key metrics and insights.

## 3. Presenting Findings

### 3.1 Prepare Your Presentation

1. **Summarize Key Insights**:
   - Highlight key findings from your analysis, such as average salaries by department, trends in employee age, and any notable outliers.

2. **Create Visualizations**:
   - Use the charts and graphs you created to support your findings.

### 3.2 Create a Report

1. **Compile Your Analysis**:
   - Prepare a report that includes:
     - Introduction to the dataset and analysis goals.
     - Data cleaning steps and challenges faced.
     - EDA findings with visualizations.
     - Statistical analysis results.
     - Conclusion and recommendations based on your findings.

2. **Use Excel or a Presentation Tool**:
   - You can present your findings using Excel, PowerPoint, or any other presentation tool of your choice.

## Conclusion

In this final project, you applied the skills learned throughout the course to analyze a real-world dataset. By following the steps of data cleaning, exploratory data analysis, statistical analysis, and visualization, you gained valuable insights that can inform decision-making. This project serves as a culmination of your learning and prepares you for future data analysis tasks.