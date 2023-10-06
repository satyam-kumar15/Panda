# Panda 
Explanation of Concepts:

1. **Importing pandas**:

```python
import pandas as pd
```

This line imports the pandas library and gives it the alias `pd`, which is a common convention.

2. **Creating a DataFrame**:

```python
data = {'Name': ['John', 'Anna', 'Peter', 'Linda'],
        'Age': [28, 25, 32, 29],
        'City': ['New York', 'Paris', 'Berlin', 'London']}

df = pd.DataFrame(data)
```

Here, we create a DataFrame from a dictionary. Each key becomes a column name, and the corresponding list becomes the data in that column.

3. **Reading Data from a CSV File**:

```python
csv_data = pd.read_csv('data.csv')
```

This reads data from a CSV file and creates a DataFrame.

4. **Viewing Data**:

```python
head = df.head()
tail = df.tail()
shape = df.shape
info = df.info()
```

- `head()` and `tail()` show the first and last few rows of the DataFrame, respectively.
- `shape` returns the number of rows and columns.
- `info()` provides a summary of the DataFrame, including data types and non-null counts.

5. **Indexing and Selecting Data**:

```python
name_column = df['Name']
subset = df[['Name', 'Age']]
row = df.iloc[0]
subset_rows = df.iloc[1:3]
subset_condition = df[df['Age'] > 28]
```

- `df['Name']` selects the 'Name' column.
- `df[['Name', 'Age']]` selects multiple columns.
- `df.iloc[0]` selects the first row.
- `df.iloc[1:3]` selects rows 2 and 3.
- `df[df['Age'] > 28]` filters rows where 'Age' is greater than 28.

6. **Descriptive Statistics**:

```python
describe = df.describe()
mean_age = df['Age'].mean()
```

- `describe()` provides summary statistics like mean, min, max, etc.
- `df['Age'].mean()` calculates the mean of the 'Age' column.

7. **Missing Data**:

```python
na_check = df.isna()
filled_na = df.fillna(0)
drop_na = df.dropna()
```

- `df.isna()` checks for missing values.
- `df.fillna(0)` fills missing values with 0.
- `df.dropna()` drops rows with missing values.

8. **Grouping and Aggregation**:

```python
grouped = df.groupby('City').mean()
```

This groups the data by the 'City' column and calculates the mean for each group.

9. **Sorting Data**:

```python
sorted_df = df.sort_values(by='Age', ascending=False)
```

This sorts the DataFrame by the 'Age' column in descending order.

10. **Adding and Removing Columns**:

```python
df['Country'] = ['USA', 'France', 'Germany', 'UK']
df.drop('Country', axis=1, inplace=True)
```

- `df['Country'] = ...` adds a new column 'Country'.
- `df.drop('Country', axis=1, inplace=True)` removes the 'Country' column.

11. **Applying Functions**:

```python
def double_age(age):
    return age * 2

df['Doubled Age'] = df['Age'].apply(double_age)
```

This

 applies the function `double_age` to the 'Age' column and creates a new column 'Doubled Age' with the result.

12. **Merging DataFrames**:

```python
merged_df = pd.merge(df1, df2, on='ID', how='inner')
```

This merges two DataFrames (`df1` and `df2`) on the 'ID' column using an inner join.

13. **Concatenating DataFrames**:

```python
concatenated_df = pd.concat([df1, df2], axis=0)
```

This concatenates `df1` and `df2` along the rows (`axis=0`).

14. **Handling Dates**:

```python
date_df['Date'] = pd.to_datetime(date_df['Date'])
date_df['Month'] = date_df['Date'].dt.month
```

- `pd.to_datetime()` converts a string to a datetime object.
- `date_df['Date'].dt.month` extracts the month from the date.

15. **Pivot Tables**:

```python
pivot_table = df.pivot_table(values='Age', index='City', columns='Name', fill_value=0)
```

This creates a pivot table using the values in the 'Age' column, with 'City' as the index and 'Name' as the columns.

