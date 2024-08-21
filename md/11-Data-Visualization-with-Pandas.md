# Lesson 11: Data Visualization with Pandas

## Objectives
By the end of this lesson, you will be able to:
- Understand the basics of Matplotlib and Seaborn for data visualization.
- Create various types of plots directly from Pandas DataFrames.

## 1. Introduction to Matplotlib and Seaborn

Data visualization is a critical aspect of data analysis, helping to communicate insights effectively. Two popular libraries for creating visualizations in Python are **Matplotlib** and **Seaborn**.

### 1.1 Matplotlib

Matplotlib is a widely used plotting library in Python. It provides a flexible framework for creating static, animated, and interactive visualizations.

- **Installation**: If you haven't installed Matplotlib yet, you can do so using pip:
  ```bash
  pip install matplotlib
  ```

- **Basic Usage**: The simplest way to create a plot with Matplotlib is to use the `pyplot` module.

### 1.2 Seaborn

Seaborn is built on top of Matplotlib and provides a high-level interface for drawing attractive statistical graphics. It simplifies the process of creating complex visualizations.

- **Installation**: If you haven't installed Seaborn yet, you can do so using pip:
  ```bash
  pip install seaborn
  ```

- **Features**: Seaborn comes with several built-in themes and color palettes to make visualizations more aesthetically pleasing.

## 2. Creating Plots Directly from Pandas DataFrames

Pandas integrates well with Matplotlib and Seaborn, allowing you to create plots directly from DataFrames. Below are some common types of plots you can create.

### 2.1 Line Plot

A line plot is useful for visualizing trends over time.

#### Example:

1. **Create a Sample DataFrame**:
   ```python
   import pandas as pd
   import matplotlib.pyplot as plt

   data = {
       'Month': ['January', 'February', 'March', 'April', 'May'],
       'Sales': [200, 300, 400, 500, 600]
   }

   df = pd.DataFrame(data)
   ```

2. **Create a Line Plot**:
   ```python
   # Create a line plot
   df.plot(x='Month', y='Sales', kind='line', marker='o')
   plt.title('Monthly Sales')
   plt.xlabel('Month')
   plt.ylabel('Sales')
   plt.grid()
   plt.show()
   ```

### 2.2 Bar Plot

A bar plot is useful for comparing quantities across different categories.

#### Example:

1. **Create a Bar Plot**:
   ```python
   # Create a bar plot
   df.plot(x='Month', y='Sales', kind='bar', color='skyblue')
   plt.title('Monthly Sales')
   plt.xlabel('Month')
   plt.ylabel('Sales')
   plt.xticks(rotation=45)
   plt.show()
   ```

### 2.3 Histogram

A histogram is useful for visualizing the distribution of numerical data.

#### Example:

1. **Create a Sample DataFrame**:
   ```python
   # Create a DataFrame with random data
   import numpy as np

   data = {
       'Scores': np.random.randint(0, 100, size=100)
   }

   df_scores = pd.DataFrame(data)
   ```

2. **Create a Histogram**:
   ```python
   # Create a histogram
   df_scores['Scores'].plot(kind='hist', bins=10, color='lightgreen', edgecolor='black')
   plt.title('Distribution of Scores')
   plt.xlabel('Scores')
   plt.ylabel('Frequency')
   plt.grid()
   plt.show()
   ```

### 2.4 Scatter Plot

A scatter plot is useful for visualizing the relationship between two numerical variables.

#### Example:

1. **Create a Sample DataFrame**:
   ```python
   data = {
       'Height': [150, 160, 170, 180, 190],
       'Weight': [50, 60, 70, 80, 90]
   }

   df_scatter = pd.DataFrame(data)
   ```

2. **Create a Scatter Plot**:
   ```python
   # Create a scatter plot
   df_scatter.plot(kind='scatter', x='Height', y='Weight', color='purple')
   plt.title('Height vs Weight')
   plt.xlabel('Height (cm)')
   plt.ylabel('Weight (kg)')
   plt.grid()
   plt.show()
   ```

### 2.5 Using Seaborn for Enhanced Visualizations

Seaborn makes it easy to create more complex visualizations with less code.

#### Example:

1. **Create a Sample DataFrame**:
   ```python
   import seaborn as sns

   data = {
       'Category': ['A', 'B', 'C', 'A', 'B', 'C'],
       'Values': [10, 20, 30, 15, 25, 35]
   }

   df_seaborn = pd.DataFrame(data)
   ```

2. **Create a Box Plot**:
   ```python
   # Create a box plot using Seaborn
   sns.boxplot(x='Category', y='Values', data=df_seaborn)
   plt.title('Box Plot of Values by Category')
   plt.show()
   ```

## Conclusion

In this lesson, we introduced Matplotlib and Seaborn as powerful tools for data visualization in Python. We demonstrated how to create various types of plots directly from Pandas DataFrames, including line plots, bar plots, histograms, scatter plots, and box plots. These visualizations are essential for analyzing data and communicating insights effectively.