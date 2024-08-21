# Lesson 5: Introduction to Data Cleaning in Excel

## Objectives
By the end of this lesson, you will be able to:
- Identify and handle missing or incorrect data in Excel.
- Use Excel's sorting and filtering features to organize and analyze data effectively.

## 1. Identifying and Handling Missing or Incorrect Data

Data cleaning is an essential step in the data analysis process. It involves identifying and correcting errors or inconsistencies in your dataset to ensure accuracy and reliability.

### 1.1 Identifying Missing Data

Missing data can occur for various reasons, such as incomplete surveys or data entry errors. Here are some ways to identify missing data in Excel:

- **Visual Inspection**: Look for blank cells in your dataset. These may indicate missing values.

- **Using Conditional Formatting**:
  1. Select the range of data you want to check.
  2. Go to the **Home** tab in the Ribbon.
  3. Click on **Conditional Formatting** > **New Rule**.
  4. Choose **Format only cells that contain** and set the rule to format cells that are **Blanks**.
  5. Choose a formatting style (e.g., fill color) and click **OK**. This will highlight all blank cells.

### 1.2 Handling Missing Data

Once you identify missing data, you can handle it in several ways:

- **Deleting Rows**: If a row contains missing data that is not critical, you can delete the entire row.
  - Select the row by right-clicking on the row number and choosing **Delete**.

- **Filling in Missing Values**: If the missing data can be estimated or filled in, you can enter the appropriate values manually or use Excel functions.
  - **Using the AVERAGE Function**: For numerical data, you can replace missing values with the average of the available data.
    ```excel
    =IF(ISBLANK(A2), AVERAGE(A:A), A2)
    ```
  - **Using the Fill Handle**: If the missing data follows a pattern, you can use the fill handle to copy values from adjacent cells.

- **Using Find and Replace**: If you have common incorrect values (e.g., "N/A" or "Unknown"), you can quickly replace them:
  1. Press `Ctrl + H` to open the Find and Replace dialog.
  2. Enter the incorrect value in the **Find what** box and the correct value in the **Replace with** box.
  3. Click **Replace All** to correct all instances.

## 2. Using Excel's Sorting and Filtering Features

Sorting and filtering are powerful tools in Excel that help you organize and analyze your data more effectively.

### 2.1 Sorting Data

Sorting allows you to arrange your data in a specific order (ascending or descending) based on one or more columns.

#### Steps to Sort Data:

1. **Select Your Data**: Click anywhere in the range of data you want to sort.

2. **Go to the Data Tab**: Click on the **Data** tab in the Ribbon.

3. **Choose Sort Options**:
   - Click on the **Sort A to Z** button to sort alphabetically or numerically in ascending order.
   - Click on the **Sort Z to A** button to sort in descending order.

4. **Custom Sort**:
   - For more sorting options, click on the **Sort** button in the Data tab.
   - In the Sort dialog, choose the column you want to sort by from the dropdown.
   - Select whether to sort in ascending or descending order.
   - You can add more levels to sort by clicking on **Add Level**.

### 2.2 Filtering Data

Filtering allows you to display only the rows that meet specific criteria, making it easier to analyze subsets of your data.

#### Steps to Filter Data:

1. **Select Your Data**: Click anywhere in the range of data you want to filter.

2. **Go to the Data Tab**: Click on the **Data** tab in the Ribbon.

3. **Enable Filtering**:
   - Click on the **Filter** button. This will add dropdown arrows to the header row of your data.

4. **Apply a Filter**:
   - Click the dropdown arrow in the header of the column you want to filter.
   - You can filter by specific values, text, or numerical ranges.
   - Check or uncheck the boxes next to the values you want to display.
   - Click **OK** to apply the filter.

5. **Clear Filters**: To remove filters, click the **Filter** button again or select **Clear Filter from [Column Name]** from the dropdown menu.

## Conclusion

In this lesson, we learned how to identify and handle missing or incorrect data in Excel. We also explored Excel's sorting and filtering features, which help organize and analyze data effectively.

### Next Steps
- Practice identifying and handling missing data in your own datasets.
- Experiment with sorting and filtering to analyze different subsets of your data.
