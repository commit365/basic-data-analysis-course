# Lesson 9: Data Cleaning and Preparation in Pandas

## Objectives
By the end of this lesson, you will be able to:
- Handle missing data in a DataFrame using drop and fill methods.
- Rename columns and filter rows based on specific conditions.

## 1. Handling Missing Data

Missing data is a common issue in data analysis, and Pandas provides several methods to handle it effectively. You can either drop missing values or fill them with specific values.

### 1.1 Dropping Missing Data

You can remove rows or columns with missing data using the `dropna()` method.

#### Example:

1. **Create a Sample DataFrame**:
   ```python
   import pandas as pd

   data = {
       'Name': ['Alice', 'Bob', None, 'Charlie'],
       'Age': [25, None, 30, 35],
       'City': ['New York', 'Los Angeles', 'Chicago', None]
   }

   df = pd.DataFrame(data)
   print("Original DataFrame:")
   print(df)
   ```

   #### Output:
   ```
         Name   Age         City
   0    Alice  25.0     New York
   1      Bob   NaN  Los Angeles
   2    None  30.0      Chicago
   3  Charlie  35.0        None
   ```

2. **Drop Rows with Missing Values**:
   ```python
   # Drop rows with any missing values
   df_dropped = df.dropna()
   print("\nDataFrame after dropping rows with missing values:")
   print(df_dropped)
   ```

   #### Output:
   ```
         Name   Age      City
   0    Alice  25.0  New York
   ```

3. **Drop Columns with Missing Values**:
   ```python
   # Drop columns with any missing values
   df_dropped_columns = df.dropna(axis=1)
   print("\nDataFrame after dropping columns with missing values:")
   print(df_dropped_columns)
   ```

   #### Output:
   ```
         Name
   0    Alice
   1      Bob
   2    None
   3  Charlie
   ```

### 1.2 Filling Missing Data

You can fill missing values using the `fillna()` method. This is useful when you want to retain the data structure but replace missing values with meaningful data.

#### Example:

1. **Fill Missing Values with a Specific Value**:
   ```python
   # Fill missing values with a specific value (e.g., 'Unknown' for strings and 0 for numbers)
   df_filled = df.fillna({'Name': 'Unknown', 'Age': 0, 'City': 'Unknown'})
   print("\nDataFrame after filling missing values:")
   print(df_filled)
   ```

   #### Output:
   ```
         Name   Age         City
   0    Alice  25.0     New York
   1  Unknown   0.0  Los Angeles
   2  Unknown  30.0      Chicago
   3  Charlie  35.0      Unknown
   ```

2. **Fill Missing Values with the Previous Value**:
   ```python
   # Fill missing values with the previous value in the column
   df_filled_forward = df.fillna(method='ffill')
   print("\nDataFrame after forward filling missing values:")
   print(df_filled_forward)
   ```

   #### Output:
   ```
         Name   Age         City
   0    Alice  25.0     New York
   1      Bob  25.0  Los Angeles
   2      Bob  30.0      Chicago
   3  Charlie  35.0      Chicago
   ```

## 2. Renaming Columns

Renaming columns in a DataFrame can help make your data more understandable and easier to work with. You can use the `rename()` method to change column names.

### Example:

1. **Rename Columns**:
   ```python
   # Rename columns using a dictionary
   df_renamed = df.rename(columns={'Name': 'Full Name', 'Age': 'Age (Years)', 'City': 'Location'})
   print("\nDataFrame after renaming columns:")
   print(df_renamed)
   ```

   #### Output:
   ```
     Full Name  Age (Years)     Location
   0      Alice          25.0     New York
   1        Bob           NaN  Los Angeles
   2      Unknown        30.0      Chicago
   3   Charlie          35.0        None
   ```

## 3. Filtering Rows

Filtering rows allows you to create a subset of your DataFrame based on specific conditions. You can use boolean indexing to filter rows.

### Example:

1. **Filter Rows Based on a Condition**:
   ```python
   # Filter rows where Age is greater than 30
   df_filtered = df[df['Age'] > 30]
   print("\nDataFrame after filtering rows where Age > 30:")
   print(df_filtered)
   ```

   #### Output:
   ```
         Name   Age      City
   3  Charlie  35.0      None
   ```

2. **Filter Rows Based on Multiple Conditions**:
   ```python
   # Filter rows where Age is greater than 25 and City is not None
   df_filtered_multiple = df[(df['Age'] > 25) & (df['City'].notna())]
   print("\nDataFrame after filtering rows where Age > 25 and City is not None:")
   print(df_filtered_multiple)
   ```

   #### Output:
   ```
         Name   Age         City
   2    None  30.0      Chicago
   3  Charlie  35.0        None
   ```

## Conclusion

In this lesson, we covered essential data cleaning and preparation techniques in Pandas. We learned how to handle missing data by dropping or filling values, rename columns for clarity, and filter rows based on specific conditions. These skills are crucial for preparing your data for analysis and ensuring its quality.