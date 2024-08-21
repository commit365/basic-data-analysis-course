# Lesson 14: Exploratory Data Analysis (EDA) with Pandas

## Objectives
By the end of this lesson, you will be able to:
- Perform Exploratory Data Analysis (EDA) to uncover patterns and insights in datasets.
- Visualize distributions and relationships within the data using Pandas and Matplotlib/Seaborn.

## 1. Performing EDA to Uncover Patterns and Insights

Exploratory Data Analysis (EDA) is the process of analyzing datasets to summarize their main characteristics, often using visual methods. EDA helps you understand the data, identify patterns, detect anomalies, and formulate hypotheses.

### 1.1 Loading the Dataset

First, you need to load your dataset into a Pandas DataFrame. For this example, let’s assume you have a CSV file named `data.csv` with the following columns: `Age`, `Salary`, `Department`, and `Years of Experience`.

#### Example:

```python
import pandas as pd

# Load the dataset
df = pd.read_csv('data.csv')

# Display the first few rows of the DataFrame
print(df.head())
```

### 1.2 Basic Data Exploration

Before diving into visualizations, it’s essential to perform some basic exploration of the dataset.

1. **Check the Shape of the DataFrame**:
   ```python
   print("Shape of the DataFrame:", df.shape)
   ```

2. **Get Summary Statistics**:
   ```python
   print("\nSummary Statistics:")
   print(df.describe())
   ```

3. **Check for Missing Values**:
   ```python
   print("\nMissing Values:")
   print(df.isnull().sum())
   ```

4. **View Data Types**:
   ```python
   print("\nData Types:")
   print(df.dtypes)
   ```

### 1.3 Identifying Patterns and Insights

You can use groupby operations to identify patterns in the data.

#### Example:

1. **Group by Department and Calculate Average Salary**:
   ```python
   avg_salary_by_dept = df.groupby('Department')['Salary'].mean()
   print("\nAverage Salary by Department:")
   print(avg_salary_by_dept)
   ```

2. **Count the Number of Employees in Each Department**:
   ```python
   employee_count_by_dept = df['Department'].value_counts()
   print("\nEmployee Count by Department:")
   print(employee_count_by_dept)
   ```

## 2. Visualizing Distributions and Relationships in Data

Visualization is a crucial part of EDA, as it allows you to see patterns and relationships more clearly.

### 2.1 Visualizing Distributions

#### Histograms

Histograms are useful for visualizing the distribution of a single numerical variable.

##### Example:

```python
import matplotlib.pyplot as plt

# Create a histogram for Salary
plt.figure(figsize=(10, 6))
plt.hist(df['Salary'], bins=10, color='skyblue', edgecolor='black')
plt.title('Distribution of Salary')
plt.xlabel('Salary')
plt.ylabel('Frequency')
plt.grid()
plt.show()
```

#### Box Plots

Box plots are useful for visualizing the distribution and identifying outliers.

##### Example:

```python
import seaborn as sns

# Create a box plot for Salary by Department
plt.figure(figsize=(10, 6))
sns.boxplot(x='Department', y='Salary', data=df)
plt.title('Box Plot of Salary by Department')
plt.xlabel('Department')
plt.ylabel('Salary')
plt.grid()
plt.show()
```

### 2.2 Visualizing Relationships

#### Scatter Plots

Scatter plots are useful for visualizing the relationship between two numerical variables.

##### Example:

```python
# Create a scatter plot for Salary vs. Years of Experience
plt.figure(figsize=(10, 6))
plt.scatter(df['Years of Experience'], df['Salary'], color='purple')
plt.title('Salary vs. Years of Experience')
plt.xlabel('Years of Experience')
plt.ylabel('Salary')
plt.grid()
plt.show()
```

#### Pair Plots

Pair plots allow you to visualize relationships between multiple numerical variables in a dataset.

##### Example:

```python
# Create a pair plot
sns.pairplot(df)
plt.title('Pair Plot of Numerical Variables')
plt.show()
```

## Conclusion

In this lesson, we explored the fundamentals of Exploratory Data Analysis (EDA) using Pandas. We learned how to perform basic data exploration to uncover patterns and insights, as well as how to visualize distributions and relationships within the data using various plotting techniques. EDA is a critical step in the data analysis process, helping to inform further analysis and decision-making.