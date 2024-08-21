# Lesson 12: Combining Data from Multiple Sources in Excel

## Objectives
By the end of this lesson, you will be able to:
- Use Excel’s Power Query to merge datasets from multiple sources.
- Understand data relationships and different types of joins.

## 1. Using Excel’s Power Query to Merge Datasets

Power Query is a powerful tool in Excel that allows you to import, transform, and combine data from various sources. It provides an intuitive interface for merging datasets.

### 1.1 Importing Data with Power Query

1. **Open Power Query**:
   - In Excel, go to the **Data** tab on the Ribbon.
   - Click on **Get Data** > **From File** > **From Workbook** (or choose another source like CSV, Text, or Web).

2. **Select Your File**:
   - Navigate to the location of your file and select it. Click **Import**.

3. **Select the Data**:
   - In the Navigator window, select the sheet or table you want to import. Click **Load** to load it directly into Excel, or click **Transform Data** to open it in Power Query Editor for further manipulation.

### 1.2 Merging Datasets

To combine data from multiple sources, you can merge datasets in Power Query.

1. **Load Multiple Datasets**:
   - Repeat the import process for each dataset you want to merge.

2. **Open Power Query Editor**:
   - After loading the datasets, go to the **Data** tab and click on **Get Data** > **Launch Power Query Editor**.

3. **Merge Queries**:
   - In the Power Query Editor, select the first query (dataset) you want to merge.
   - Click on the **Home** tab, then select **Merge Queries**. Choose **Merge Queries as New** if you want to create a new query.

4. **Select the Second Dataset**:
   - In the Merge dialog, select the second dataset from the dropdown menu.
   - Choose the columns you want to use for the merge from both datasets. Ensure that the columns have matching data types.

5. **Choose the Join Type**:
   - Select the type of join you want to perform (Inner, Left Outer, Right Outer, Full Outer, etc.). The default is an Inner join, which only includes matching rows from both datasets.

6. **Click OK**:
   - After selecting the join type, click **OK**. This will create a new merged query.

7. **Expand the Merged Column**:
   - In the new merged query, you will see a column with a table icon. Click the expand icon (two arrows) in the column header to choose which columns from the second dataset you want to include in the merged dataset.

8. **Load the Merged Data**:
   - Once you have finished merging and transforming your data, click **Close & Load** to load the merged dataset back into Excel.

## 2. Understanding Data Relationships and Joins

When combining datasets, it’s essential to understand data relationships and how different types of joins affect the resulting dataset.

### 2.1 Data Relationships

Data relationships define how data in one table relates to data in another table. In Excel, relationships can be established through common fields (keys) between tables.

- **Primary Key**: A unique identifier for each record in a table (e.g., Employee ID).
- **Foreign Key**: A field in one table that uniquely identifies a row of another table (e.g., Department ID in an Employee table).

### 2.2 Types of Joins

When merging datasets, different types of joins determine how records from each dataset are combined:

1. **Inner Join**:
   - Returns only the rows that have matching values in both datasets.
   - Example: If you have a list of employees and a list of departments, an inner join will return only the employees that belong to a department.

2. **Left Outer Join**:
   - Returns all rows from the left dataset and the matched rows from the right dataset. If there is no match, NULL values are returned for columns from the right dataset.
   - Example: All employees will be listed, even if they do not belong to a department.

3. **Right Outer Join**:
   - Returns all rows from the right dataset and the matched rows from the left dataset. If there is no match, NULL values are returned for columns from the left dataset.
   - Example: All departments will be listed, even if there are no employees assigned to them.

4. **Full Outer Join**:
   - Returns all rows when there is a match in either dataset. If there is no match, NULL values are returned for the non-matching side.
   - Example: All employees and all departments will be listed, with NULLs where there are no matches.

5. **Cross Join**:
   - Returns the Cartesian product of the two datasets, meaning every row from the first dataset is combined with every row from the second dataset.
   - Example: If you have 3 employees and 2 departments, a cross join will result in 6 combinations.

## Conclusion

In this lesson, we learned how to use Excel’s Power Query to merge datasets from multiple sources, providing a powerful way to combine and analyze data. We also explored the concept of data relationships and different types of joins, which are essential for understanding how data from multiple tables can be combined effectively.