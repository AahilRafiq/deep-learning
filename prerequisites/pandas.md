# Pandas DataFrame UltraQuick Tutorial

A DataFrame is similar to an in-memory spreadsheet. Like a spreadsheet:

  * A DataFrame stores data in cells.
  * A DataFrame has named columns (usually) and numbered rows.

## Import NumPy and pandas modules

Run the following code cell to import the NumPy and pandas modules.


```python
import numpy as np
import pandas as pd
```

## Creating a DataFrame

The following code cell creates a simple DataFrame containing 10 cells organized as follows:

  * 5 rows
  * 2 columns, one named `temperature` and the other named `activity`

The following code cell instantiates a `pd.DataFrame` class to generate a DataFrame. The class takes two arguments:

  * The first argument provides the data to populate the 10 cells. The code cell calls `np.array` to generate the 5x2 NumPy array.
  * The second argument identifies the names of the two columns.


```python
# Create and populate a 5x2 NumPy array.
my_data = np.array([[0, 3], [10, 7], [20, 9], [30, 14], [40, 15]])

# Create a Python list that holds the names of the two columns.
my_column_names = ['temperature', 'activity']

# Create a DataFrame.
my_dataframe = pd.DataFrame(data=my_data, columns=my_column_names)

# Print the entire DataFrame
print(my_dataframe)
```

       temperature  activity
    0            0         3
    1           10         7
    2           20         9
    3           30        14
    4           40        15


## Adding a new column to a DataFrame

You may add a new column to an existing pandas DataFrame just by assigning values to a new column name. For example, the following code creates a third column named `adjusted` in `my_dataframe`:


```python
# Create a new column named adjusted.
# adjust column takes values of activity column and adds 2 to each value (broadcasting)
my_dataframe["adjusted"] = my_dataframe["activity"] + 2

# Print the entire DataFrame
print(my_dataframe)
```

       temperature  activity  adjusted
    0            0         3         5
    1           10         7         9
    2           20         9        11
    3           30        14        16
    4           40        15        17


## Specifying a subset of a DataFrame

Pandas provide multiples ways to isolate specific rows, columns, slices or cells in a DataFrame.


```python
print("Rows #0, #1, and #2:")
print(my_dataframe.head(3), '\n')

print("Row #2:")
print(my_dataframe.iloc[[2]], '\n')

print("Rows #1, #2, and #3:")
print(my_dataframe[1:4], '\n')

print("Column 'temperature':")
print(my_dataframe['temperature'])
```

    Rows #0, #1, and #2:
       temperature  activity  adjusted
    0            0         3         5
    1           10         7         9
    2           20         9        11 
    
    Row #2:
       temperature  activity  adjusted
    2           20         9        11 
    
    Rows #1, #2, and #3:
       temperature  activity  adjusted
    1           10         7         9
    2           20         9        11
    3           30        14        16 
    
    Column 'temperature':
    0     0
    1    10
    2    20
    3    30
    4    40
    Name: temperature, dtype: int64


## Task 1: Create a DataFrame

Do the following:

  1. Create an 3x4 (3 rows x 4 columns) pandas DataFrame in which the columns are named `Eleanor`,  `Chidi`, `Tahani`, and `Jason`.  Populate each of the 12 cells in the DataFrame with a random integer between 0 and 100, inclusive.

  2. Output the following:

     * the entire DataFrame
     * the value in the cell of row #1 of the `Eleanor` column

  3. Create a fifth column named `Janet`, which is populated with the row-by-row sums of `Tahani` and `Jason`.

To complete this task, it helps to know the NumPy basics covered in the NumPy UltraQuick Tutorial.



```python
columns = ["Eleanor","Chidi","Tahani","Jason"]
data = np.random.randint(low=0,high=101,size=(3,4))
dataframe = pd.DataFrame(data=data,columns=columns)
dataframe["Janet"] = dataframe["Tahani"]-dataframe["Jason"]
print(dataframe)
```
