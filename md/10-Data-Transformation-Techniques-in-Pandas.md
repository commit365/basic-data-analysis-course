# Lesson 10: Data Transformation Techniques in Pandas

## Objectives
By the end of this lesson, you will be able to:
- Apply functions to columns and rows in a DataFrame.
- Group data and use aggregation functions to summarize information.

## 1. Applying Functions to Columns and Rows

Pandas allows you to apply functions to individual columns or rows using the `apply()` method. This is useful for transforming data based on specific calculations or operations.

### 1.1 Applying Functions to Columns

You can apply a function to an entire column by passing the function to the `apply()` method.

#### Example:

1. **Create a Sample DataFrame**:
   ```python
   import pandas as pd

   data = {
       'Name': ['Alice', 'Bob', 'Charlie'],
       'Age': [25, 30, 35],
       'Salary': [50000, 60000, 70000]
   }

   df = pd.DataFrame(data)
   print("Original DataFrame:")
   print(df)
   ```

   #### Output:
   ```
       Name  Age  Salary
   0  Alice   25   50000
   1    Bob   30   60000
   2 Charlie   35   70000
   ```

2. **Apply a Function to a Column**:
   - Suppose you want to increase each salary by 10%. You can define a function and apply it to the `Salary` column:
   ```python
   # Define a function to increase salary by 10%
   def increase_salary(salary):
       return salary * 1.10

   # Apply the function to the Salary column
   df['Salary'] = df['Salary'].apply(increase_salary)
   print("\nDataFrame after increasing salaries by 10%:")
   print(df)
   ```

   #### Output:
   ```
       Name  Age   Salary
   0  Alice   25  55000.0
   1    Bob   30  66000.0
   2 Charlie   35  77000.0
   ```

### 1.2 Applying Functions to Rows

You can also apply a function across rows by using the `axis` parameter in the `apply()` method.

#### Example:

1. **Apply a Function to Rows**:
   - Suppose you want to create a new column that categorizes employees based on their age:
   ```python
   # Define a function to categorize age
   def categorize_age(age):
       if age < 30:
           return 'Young'
       elif age < 40:
           return 'Middle-aged'
       else:
           return 'Senior'

   # Apply the function to the Age column to create a new column
   df['Age Category'] = df['Age'].apply(categorize_age)
   print("\nDataFrame after adding Age Category:")
   print(df)
   ```

   #### Output:
   ```
       Name  Age   Salary    Age Category
   0  Alice   25  55000.0           Young
   1    Bob   30  66000.0   Middle-aged
   2 Charlie   35  77000.0   Middle-aged
   ```

## 2. Grouping Data and Using Aggregation Functions

Grouping data allows you to summarize and analyze subsets of your data. You can use the `groupby()` method to group data based on one or more columns and apply aggregation functions to summarize the results.

### 2.1 Grouping Data

#### Example:

1. **Create a Sample DataFrame**:
   ```python
   data = {
       'Department': ['HR', 'IT', 'HR', 'IT', 'Finance'],
       'Employee': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
       'Salary': [50000, 60000, 55000, 62000, 70000]
   }

   df = pd.DataFrame(data)
   print("Original DataFrame:")
   print(df)
   ```

   #### Output:
   ```
     Department Employee  Salary
   0         HR    Alice   50000
   1         IT      Bob   60000
   2         HR  Charlie   55000
   3         IT    David   62000
   4     Finance      Eve   70000
   ```

2. **Group by Department**:
   - Group the data by the `Department` column and calculate the average salary for each department:
   ```python
   # Group by Department and calculate the average salary
   avg_salary = df.groupby('Department')['Salary'].mean()
   print("\nAverage Salary by Department:")
   print(avg_salary)
   ```

   #### Output:
   ```
   Department
   Finance    70000.0
   HR         52500.0
   IT         61000.0
   Name: Salary, dtype: float64
   ```

### 2.2 Using Aggregation Functions

You can use various aggregation functions to summarize data, such as `sum()`, `count()`, `min()`, and `max()`.

#### Example:

1. **Multiple Aggregations**:
   - You can apply multiple aggregation functions at once using the `agg()` method:
   ```python
   # Group by Department and apply multiple aggregation functions
   salary_summary = df.groupby('Department')['Salary'].agg(['mean', 'sum', 'count'])
   print("\nSalary Summary by Department:")
   print(salary_summary)
   ```

   #### Output:
   ```
               mean   sum  count
   Department                     
   Finance   70000.0  70000      1
   HR        52500.0 105000      2
   IT        61000.0 122000      2
   ```

## Conclusion

In this lesson, we explored data transformation techniques in Pandas. We learned how to apply functions to columns and rows to manipulate data effectively. We also covered how to group data and use aggregation functions to summarize information, which is essential for analyzing datasets and extracting meaningful insights.