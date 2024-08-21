# Lesson 3: Basic Excel Functions and Formulas

## Objectives
By the end of this lesson, you will be able to:
- Understand and use essential Excel functions such as SUM, AVERAGE, and COUNT.
- Create and utilize simple formulas in Excel.

## 1. Introduction to Essential Functions

Excel provides a variety of built-in functions that allow you to perform calculations and analyze data quickly. In this section, we will cover three essential functions: **SUM**, **AVERAGE**, and **COUNT**.

### 1.1 SUM Function

- **Purpose**: The SUM function adds together a range of numbers.
- **Syntax**: 
  ```excel
  =SUM(number1, [number2], ...)
  ```
  - **number1**: The first number or range to sum.
  - **[number2]**: Additional numbers or ranges (optional).

**Example**:
To sum the values in cells A1 to A5, you would enter:
```excel
=SUM(A1:A5)
```

### 1.2 AVERAGE Function

- **Purpose**: The AVERAGE function calculates the mean (average) of a group of numbers.
- **Syntax**: 
  ```excel
  =AVERAGE(number1, [number2], ...)
  ```
  - **number1**: The first number or range to average.
  - **[number2]**: Additional numbers or ranges (optional).

**Example**:
To find the average of the values in cells B1 to B5, you would enter:
```excel
=AVERAGE(B1:B5)
```

### 1.3 COUNT Function

- **Purpose**: The COUNT function counts the number of cells that contain numeric values within a specified range.
- **Syntax**: 
  ```excel
  =COUNT(value1, [value2], ...)
  ```
  - **value1**: The first value or range to count.
  - **[value2]**: Additional values or ranges (optional).

**Example**:
To count the number of numeric entries in cells C1 to C5, you would enter:
```excel
=COUNT(C1:C5)
```

## 2. Creating and Using Simple Formulas

Formulas in Excel allow you to perform calculations using cell references, constants, and functions. Here’s how to create and use simple formulas.

### 2.1 Basic Formula Structure

- **Start with an Equal Sign**: Every formula must begin with an equal sign (`=`).
- **Use Cell References**: Instead of using actual numbers, you can use cell references to create dynamic formulas that update automatically when the data changes.

### 2.2 Example of a Simple Formula

Let’s create a formula that calculates the total cost of items based on their quantity and price.

1. **Set Up Your Data**:
   - In cell A1, enter "Quantity".
   - In cell B1, enter "Price".
   - In cell C1, enter "Total Cost".
   - In cells A2 to A5, enter quantities (e.g., 2, 3, 5, 1).
   - In cells B2 to B5, enter prices (e.g., 10, 15, 20, 5).

2. **Create the Formula**:
   - Click on cell C2 to select it.
   - Enter the formula to calculate total cost:
     ```excel
     =A2*B2
     ```
   - Press `Enter`. This will calculate the total cost for the first item.

3. **Copy the Formula**:
   - To apply the same formula to the other rows, click on the small square at the bottom right corner of cell C2 (the fill handle) and drag it down to cell C5. This will copy the formula and adjust the cell references automatically.

### 2.3 Using Functions in Formulas

You can also combine functions within formulas. For example, if you want to calculate the total cost for all items:

1. **Create a New Cell for Total**:
   - In cell C6, enter "Total Cost for All Items".

2. **Use the SUM Function**:
   - In cell D6, enter the formula:
     ```excel
     =SUM(C2:C5)
     ```
   - Press `Enter`. This will sum the total costs of all items.

## Conclusion

In this lesson, we explored essential Excel functions such as SUM, AVERAGE, and COUNT, which are fundamental for data analysis. We also learned how to create and use simple formulas to perform calculations dynamically.

### Next Steps
- Practice using the functions and formulas covered in this lesson by creating your own data set.
- Experiment with combining different functions in your formulas to enhance your calculations.
