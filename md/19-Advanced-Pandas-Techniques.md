# Lesson 19: Advanced Pandas Techniques

## Objectives
By the end of this lesson, you will be able to:
- Merge and join DataFrames in Pandas.
- Perform time series analysis using Pandas.

## 1. Merging and Joining DataFrames

Merging and joining DataFrames are essential techniques for combining datasets based on common keys or indices. Pandas provides several functions to facilitate these operations.

### 1.1 Merging DataFrames

The `merge()` function is used to combine two DataFrames based on one or more keys.

#### Example:

1. **Create Sample DataFrames**:
   ```python
   import pandas as pd

   # Create the first DataFrame
   df1 = pd.DataFrame({
       'EmployeeID': [1, 2, 3],
       'Name': ['Alice', 'Bob', 'Charlie']
   })

   # Create the second DataFrame
   df2 = pd.DataFrame({
       'EmployeeID': [1, 2, 4],
       'Department': ['HR', 'IT', 'Finance']
   })
   ```

2. **Merge the DataFrames**:
   ```python
   # Merge DataFrames on EmployeeID
   merged_df = pd.merge(df1, df2, on='EmployeeID', how='inner')  # Inner join by default
   print("Merged DataFrame (Inner Join):")
   print(merged_df)
   ```

   #### Output:
   ```
      EmployeeID     Name Department
   0           1    Alice         HR
   1           2      Bob         IT
   ```

### 1.2 Types of Joins

You can specify different types of joins using the `how` parameter in the `merge()` function:

- **Inner Join**: Returns only the rows with matching keys in both DataFrames.
- **Outer Join**: Returns all rows from both DataFrames, filling in NaNs where there are no matches.
- **Left Join**: Returns all rows from the left DataFrame and matching rows from the right DataFrame.
- **Right Join**: Returns all rows from the right DataFrame and matching rows from the left DataFrame.

#### Example of Outer Join:

```python
# Merge DataFrames with an outer join
outer_merged_df = pd.merge(df1, df2, on='EmployeeID', how='outer')
print("\nMerged DataFrame (Outer Join):")
print(outer_merged_df)
```

#### Output:
```
   EmployeeID     Name Department
0           1    Alice         HR
1           2      Bob         IT
2           3  Charlie       NaN
3           4      NaN   Finance
```

## 2. Joining DataFrames

The `join()` method is used to join two DataFrames based on their indices.

### Example:

1. **Create Sample DataFrames**:
   ```python
   df3 = pd.DataFrame({
       'Department': ['HR', 'IT', 'Finance'],
       'Budget': [50000, 60000, 70000]
   }, index=[1, 2, 4])  # Custom index
   ```

2. **Join DataFrames**:
   ```python
   # Join df1 with df3 using the index
   joined_df = df1.set_index('EmployeeID').join(df3)
   print("\nJoined DataFrame:")
   print(joined_df)
   ```

#### Output:
```
             Name Department   Budget
   EmployeeID                         
   1        Alice         HR  50000.0
   2          Bob         IT  60000.0
   3      Charlie       NaN      NaN
```

## 3. Time Series Analysis with Pandas

Time series analysis involves analyzing data that is indexed by time. Pandas provides powerful tools for working with time series data.

### 3.1 Creating a Time Series DataFrame

1. **Create a Sample Time Series DataFrame**:
   ```python
   # Create a date range
   dates = pd.date_range(start='2023-01-01', periods=5, freq='D')

   # Create a DataFrame with a time series
   time_series_df = pd.DataFrame({
       'Date': dates,
       'Sales': [200, 220, 250, 275, 300]
   })
   time_series_df.set_index('Date', inplace=True)
   print("\nTime Series DataFrame:")
   print(time_series_df)
   ```

#### Output:
```
            Sales
Date             
2023-01-01    200
2023-01-02    220
2023-01-03    250
2023-01-04    275
2023-01-05    300
```

### 3.2 Time Series Operations

Pandas provides various functionalities for analyzing time series data.

#### Example: Resampling

You can resample time series data to different frequencies (e.g., daily to weekly).

```python
# Resample the time series to weekly frequency and sum the sales
weekly_sales = time_series_df.resample('W').sum()
print("\nWeekly Sales:")
print(weekly_sales)
```

#### Output:
```
            Sales
Date             
2023-01-01    200
2023-01-08    300
```

#### Example: Rolling Window

You can calculate rolling statistics, such as a moving average.

```python
# Calculate a 3-day moving average
time_series_df['3-Day MA'] = time_series_df['Sales'].rolling(window=3).mean()
print("\nTime Series with 3-Day Moving Average:")
print(time_series_df)
```

#### Output:
```
            Sales  3-Day MA
Date                         
2023-01-01    200       NaN
2023-01-02    220       NaN
2023-01-03    250     220.0
2023-01-04    275     245.0
2023-01-05    300     248.0
```

### 3.3 Plotting Time Series Data

You can visualize time series data using line plots.

```python
import matplotlib.pyplot as plt

# Plot the time series data
plt.figure(figsize=(10, 6))
plt.plot(time_series_df.index, time_series_df['Sales'], marker='o', label='Sales')
plt.plot(time_series_df.index, time_series_df['3-Day MA'], marker='x', label='3-Day MA', linestyle='--')
plt.title('Sales Over Time with 3-Day Moving Average')
plt.xlabel('Date')
plt.ylabel('Sales')
plt.legend()
plt.grid()
plt.show()
```

## Conclusion

In this lesson, we covered advanced Pandas techniques, including merging and joining DataFrames, as well as performing time series analysis. These skills are essential for effectively managing and analyzing complex datasets, allowing you to derive meaningful insights from your data.