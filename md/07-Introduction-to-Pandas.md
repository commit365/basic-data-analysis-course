# Lesson 7: Introduction to Pandas

## Objectives
By the end of this lesson, you will be able to:
- Install Pandas and set up your Python environment.
- Understand the concepts of DataFrames and Series in Pandas.

## 1. Installing Pandas and Setting Up Your Python Environment

Pandas is a powerful data manipulation and analysis library for Python. To get started, you need to install Pandas and set up your Python environment.

### 1.1 Setting Up Python

If you haven't already installed Python, follow these steps:

1. **Download Python**:
   - Go to the official Python website: [python.org](https://www.python.org/downloads/).
   - Download the latest version of Python for your operating system (Windows, macOS, or Linux).

2. **Install Python**:
   - Run the installer and follow the prompts. Make sure to check the box that says "Add Python to PATH" before clicking "Install Now."

3. **Verify Installation**:
   - Open your command prompt (Windows) or terminal (macOS/Linux).
   - Type the following command and press Enter:
     ```bash
     python --version
     ```
   - You should see the version of Python you installed.

### 1.2 Installing Pandas

You can install Pandas using pip, which is the package installer for Python. Follow these steps:

1. **Open Command Prompt or Terminal**.

2. **Install Pandas**:
   - Type the following command and press Enter:
     ```bash
     pip install pandas
     ```
   - This command will download and install the Pandas library along with its dependencies.

3. **Verify Installation**:
   - Open a Python interpreter by typing `python` in the command prompt or terminal.
   - Import Pandas by typing:
     ```python
     import pandas as pd
     ```
   - If there are no errors, Pandas is successfully installed.

## 2. Understanding DataFrames and Series

Pandas provides two primary data structures: **Series** and **DataFrames**. Understanding these structures is essential for effective data manipulation and analysis.

### 2.1 Series

A Series is a one-dimensional labeled array capable of holding any data type (integers, strings, floats, etc.). It is similar to a list or a column in a spreadsheet.

#### Creating a Series

You can create a Series from a list or array as follows:

```python
import pandas as pd

# Creating a Series from a list
data = [10, 20, 30, 40]
series = pd.Series(data)

print(series)
```

#### Output:
```
0    10
1    20
2    30
3    40
dtype: int64
```

In this example, the index is automatically generated (0, 1, 2, 3). You can also specify custom indices:

```python
# Creating a Series with custom indices
custom_series = pd.Series(data, index=['A', 'B', 'C', 'D'])

print(custom_series)
```

#### Output:
```
A    10
B    20
C    30
D    40
dtype: int64
```

### 2.2 DataFrames

A DataFrame is a two-dimensional labeled data structure with columns that can hold different data types. It is similar to a table in a database or a spreadsheet.

#### Creating a DataFrame

You can create a DataFrame from a dictionary of lists or arrays:

```python
# Creating a DataFrame from a dictionary
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Los Angeles', 'Chicago']
}

df = pd.DataFrame(data)

print(df)
```

#### Output:
```
      Name  Age         City
0    Alice   25     New York
1      Bob   30  Los Angeles
2  Charlie   35      Chicago
```

In this example, the keys of the dictionary become the column names, and the values become the data in the DataFrame.

#### Accessing Data in DataFrames

You can access data in a DataFrame using various methods:

- **Selecting a Column**:
  ```python
  print(df['Name'])
  ```

- **Selecting Multiple Columns**:
  ```python
  print(df[['Name', 'City']])
  ```

- **Selecting Rows by Index**:
  ```python
  print(df.iloc[0])  # Selects the first row
  ```

- **Selecting Rows by Condition**:
  ```python
  print(df[df['Age'] > 30])  # Selects rows where Age is greater than 30
  ```

## Conclusion

In this lesson, we covered the installation of Pandas and the setup of your Python environment. We also explored the fundamental data structures in Pandas: Series and DataFrames, which are essential for data manipulation and analysis. Understanding these concepts will provide a solid foundation for working with data in Python using Pandas.