# Lesson 15: Introduction to Statistical Analysis

## Objectives
By the end of this lesson, you will be able to:
- Understand basic statistical concepts such as mean, median, and mode.
- Use Excel and Pandas to perform basic statistical calculations.

## 1. Basic Statistical Concepts

Statistics is a branch of mathematics that deals with collecting, analyzing, interpreting, presenting, and organizing data. Here are three fundamental concepts in statistics:

### 1.1 Mean

The mean, often referred to as the average, is calculated by summing all the values in a dataset and dividing by the number of values.

#### Formula:
$$
\text{Mean} = \frac{\sum \text{values}}{N}
$$
where $$N$$ is the number of values.

### 1.2 Median

The median is the middle value of a dataset when the values are arranged in ascending or descending order. If the dataset has an even number of observations, the median is the average of the two middle values.

#### Steps to Find the Median:
1. Sort the dataset.
2. If the number of observations $$N$$ is odd, the median is the value at position $$\frac{N + 1}{2}$$.
3. If $$N$$ is even, the median is the average of the values at positions $$\frac{N}{2}$$ and $$\frac{N}{2} + 1$$.

### 1.3 Mode

The mode is the value that appears most frequently in a dataset. A dataset may have one mode, more than one mode, or no mode at all.

#### Example:
- Dataset: [1, 2, 2, 3, 4] → Mode is 2.
- Dataset: [1, 1, 2, 2, 3] → Modes are 1 and 2 (bimodal).
- Dataset: [1, 2, 3, 4] → No mode.

## 2. Using Excel for Basic Statistical Calculations

Excel provides built-in functions to calculate mean, median, and mode easily.

### 2.1 Calculating Mean in Excel

1. **Prepare Your Data**: Enter your dataset in a column (e.g., A1:A5).
2. **Use the AVERAGE Function**:
   - In a new cell, enter the formula:
     ```excel
     =AVERAGE(A1:A5)
     ```

### 2.2 Calculating Median in Excel

1. **Use the MEDIAN Function**:
   - In a new cell, enter the formula:
     ```excel
     =MEDIAN(A1:A5)
     ```

### 2.3 Calculating Mode in Excel

1. **Use the MODE Function**:
   - In a new cell, enter the formula:
     ```excel
     =MODE(A1:A5)
     ```

## 3. Using Pandas for Basic Statistical Calculations

Pandas also provides convenient methods to calculate mean, median, and mode directly from a DataFrame.

### 3.1 Calculating Mean in Pandas

#### Example:

1. **Create a Sample DataFrame**:
   ```python
   import pandas as pd

   data = {
       'Scores': [85, 90, 75, 80, 95]
   }

   df = pd.DataFrame(data)
   ```

2. **Calculate the Mean**:
   ```python
   mean_score = df['Scores'].mean()
   print("Mean Score:", mean_score)
   ```

### 3.2 Calculating Median in Pandas

#### Example:

1. **Calculate the Median**:
   ```python
   median_score = df['Scores'].median()
   print("Median Score:", median_score)
   ```

### 3.3 Calculating Mode in Pandas

#### Example:

1. **Calculate the Mode**:
   ```python
   mode_score = df['Scores'].mode()
   print("Mode Score:", mode_score[0])  # mode() returns a Series
   ```

## Conclusion

In this lesson, we introduced basic statistical concepts such as mean, median, and mode. We also demonstrated how to perform these calculations using both Excel and Pandas. Understanding these fundamental statistics is essential for analyzing data effectively and making informed decisions based on your findings.