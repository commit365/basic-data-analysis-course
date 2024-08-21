# Lesson 8: Data Manipulation with Pandas

## Objectives
By the end of this lesson, you will be able to:
- Load data from various formats, including CSV and Excel, using Pandas.
- Perform basic data exploration using methods such as `head()`, `tail()`, `info()`, and `describe()`.

## 1. Loading Data from Various Formats

Pandas provides convenient functions for loading data from different file formats. The most commonly used formats are CSV (Comma-Separated Values) and Excel files.

### 1.1 Loading Data from CSV Files

CSV files are widely used for storing tabular data. You can load a CSV file into a Pandas DataFrame using the `read_csv()` function.

#### Example:

1. **Prepare a Sample CSV File**: Create a CSV file named `data.csv` with the following content:

   ```
   Name,Age,City
   Alice,25,New York
   Bob,30,Los Angeles
   Charlie,35,Chicago
   ```

2. **Load the CSV File**:
   ```python
   import pandas as pd

   # Load the CSV file into a DataFrame
   df_csv = pd.read_csv('data.csv')

   # Display the DataFrame
   print(df_csv)
   ```

#### Output:
```
      Name  Age         City
0    Alice   25     New York
1      Bob   30  Los Angeles
2  Charlie   35      Chicago
```

### 1.2 Loading Data from Excel Files

Pandas can also read Excel files using the `read_excel()` function. You need to have the `openpyxl` or `xlrd` library installed to read Excel files.

#### Example:

1. **Prepare a Sample Excel File**: Create an Excel file named `data.xlsx` with the same content as the CSV file.

2. **Load the Excel File**:
   ```python
   # Load the Excel file into a DataFrame
   df_excel = pd.read_excel('data.xlsx')

   # Display the DataFrame
   print(df_excel)
   ```

#### Output:
```
      Name  Age         City
0    Alice   25     New York
1      Bob   30  Los Angeles
2  Charlie   35      Chicago
```

## 2. Basic Data Exploration

Once you have loaded your data into a DataFrame, you can perform basic exploration to understand its structure and contents.

### 2.1 Using `head()`

The `head()` method returns the first few rows of the DataFrame. By default, it displays the first 5 rows, but you can specify a different number.

#### Example:
```python
# Display the first 3 rows of the DataFrame
print(df_csv.head(3))
```

#### Output:
```
      Name  Age         City
0    Alice   25     New York
1      Bob   30  Los Angeles
2  Charlie   35      Chicago
```

### 2.2 Using `tail()`

The `tail()` method returns the last few rows of the DataFrame. Like `head()`, it defaults to displaying the last 5 rows.

#### Example:
```python
# Display the last 2 rows of the DataFrame
print(df_csv.tail(2))
```

#### Output:
```
      Name  Age         City
1      Bob   30  Los Angeles
2  Charlie   35      Chicago
```

### 2.3 Using `info()`

The `info()` method provides a concise summary of the DataFrame, including the number of entries, column names, data types, and memory usage.

#### Example:
```python
# Display information about the DataFrame
print(df_csv.info())
```

#### Output:
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 3 entries, 0 to 2
Data columns (total 3 columns):
 #   Column  Non-Null Count  Dtype 
---  ------  --------------  ----- 
 0   Name    3 non-null      object
 1   Age     3 non-null      int64 
 2   City    3 non-null      object
dtypes: int64(1), object(2)
memory usage: 120.0+ bytes
```

### 2.4 Using `describe()`

The `describe()` method generates descriptive statistics of the DataFrame, including count, mean, standard deviation, minimum, and maximum values for numerical columns.

#### Example:
```python
# Display descriptive statistics of the DataFrame
print(df_csv.describe())
```

#### Output:
```
             Age
count   3.000000
mean   30.000000
std    5.000000
min    25.000000
25%    27.500000
50%    30.000000
75%    32.500000
max    35.000000
```

## Conclusion

In this lesson, we learned how to load data from various formats, including CSV and Excel, into Pandas DataFrames. We also explored basic data exploration techniques using methods like `head()`, `tail()`, `info()`, and `describe()`, which help us understand the structure and summary statistics of our data. This foundational knowledge is essential for effective data manipulation and analysis using Pandas.