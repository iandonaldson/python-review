# Python Pandas Reference

A concise reference for Pandas, oriented toward users familiar with R.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Series](#series)
3. [DataFrames](#dataframes)
4. [Reading Data](#reading-data)
5. [Analyzing Data](#analyzing-data)
6. [Cleaning Data](#cleaning-data)
   - [Handling Empty Cells](#handling-empty-cells)
   - [Wrong Format](#wrong-format)
   - [Wrong Data](#wrong-data)
   - [Duplicates](#duplicates)
7. [Correlations](#correlations)
8. [Plotting](#plotting)

---

## Getting Started

Pandas is Python's primary data manipulation library (similar to dplyr/tidyverse in R).

```python
import pandas as pd
import numpy as np

# Check version
print(pd.__version__)
```
```
2.2.0
```

---

## Series

A Series is a 1D array (similar to R's vector or single column).

```python
# Create Series
s = pd.Series([10, 20, 30, 40])
print(s)
```
```
0    10
1    20
2    30
3    40
dtype: int64
```

```python
# Named indices (like named vector in R)
s = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
print(s['b'])
```
```
20
```

```python
# From dictionary
data = {'a': 10, 'b': 20, 'c': 30}
s = pd.Series(data)
print(s)
```
```
a    10
b    20
c    30
dtype: int64
```

---

## DataFrames

DataFrames are 2D tables (analogous to R's data.frame or tibble).

```python
# Create from dictionary
data = {
    'name': ['Alice', 'Bob', 'Charlie'],
    'age': [25, 30, 35],
    'city': ['NYC', 'LA', 'Chicago']
}
df = pd.DataFrame(data)
print(df)
```
```
      name  age     city
0    Alice   25      NYC
1      Bob   30       LA
2  Charlie   35  Chicago
```

```python
# Locate row by index (like df[1,] in R)
print(df.loc[0])
```
```
name     Alice
age         25
city       NYC
Name: 0, dtype: object
```

```python
# Named indices
df = pd.DataFrame(data, index=['row1', 'row2', 'row3'])
print(df.loc['row1'])
```
```
name     Alice
age         25
city       NYC
Name: row1, dtype: object
```

---

## Reading Data

```python
# Read CSV (like read.csv in R)
df = pd.read_csv('data.csv')

# Read with specific options
df = pd.read_csv('data.csv', 
                 sep=',',           # delimiter
                 header=0,          # row for column names
                 index_col=0,       # column for row names
                 na_values=['NA', ''])  # NA values

# Read JSON
df = pd.read_json('data.json')

# Read Excel
df = pd.read_excel('data.xlsx', sheet_name='Sheet1')

# Read SQL
import sqlite3
conn = sqlite3.connect('database.db')
df = pd.read_sql('SELECT * FROM table', conn)
```

---

## Analyzing Data

```python
# Example DataFrame
data = {
    'name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'age': [25, 30, 35, 28, 32],
    'salary': [50000, 60000, 75000, 55000, 65000]
}
df = pd.DataFrame(data)

# View first rows (like head() in R)
print(df.head(3))
```
```
      name  age  salary
0    Alice   25   50000
1      Bob   30   60000
2  Charlie   35   75000
```

```python
# View last rows (like tail() in R)
print(df.tail(2))
```
```
    name  age  salary
3  David   28   55000
4    Eve   32   65000
```

```python
# Get info about DataFrame (like str() in R)
print(df.info())
```
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 5 entries, 0 to 4
Data columns (total 3 columns):
 #   Column  Non-Null Count  Dtype 
---  ------  --------------  ----- 
 0   name    5 non-null      object
 1   age     5 non-null      int64 
 2   salary  5 non-null      int64 
dtypes: int64(2), object(1)
memory usage: 252.0+ bytes
None
```

```python
# Summary statistics (like summary() in R)
print(df.describe())
```
```
             age        salary
count   5.000000      5.000000
mean   30.000000  61000.000000
std     3.807887   9354.143466
min    25.000000  50000.000000
25%    28.000000  55000.000000
50%    30.000000  60000.000000
75%    32.000000  65000.000000
max    35.000000  75000.000000
```

```python
# Shape (like dim() in R)
print(df.shape)
```
```
(5, 3)
```

```python
# Column names (like names() or colnames() in R)
print(df.columns)
```
```
Index(['name', 'age', 'salary'], dtype='object')
```

---

## Cleaning Data

### Handling Empty Cells

```python
# Create DataFrame with missing values
data = {
    'name': ['Alice', 'Bob', None, 'David'],
    'age': [25, None, 35, 28],
    'salary': [50000, 60000, 75000, None]
}
df = pd.DataFrame(data)

# Check for missing values (like is.na() in R)
print(df.isnull())
```
```
    name    age  salary
0  False  False   False
1  False   True   False
2   True  False   False
3  False  False    True
```

```python
# Count missing values per column
print(df.isnull().sum())
```
```
name      1
age       1
salary    1
dtype: int64
```

```python
# Drop rows with any missing values (like na.omit() in R)
df_clean = df.dropna()
print(df_clean)
```
```
    name   age   salary
0  Alice  25.0  50000.0
```

```python
# Drop rows where all values are missing
df_clean = df.dropna(how='all')

# Drop rows with missing values in specific columns
df_clean = df.dropna(subset=['age'])

# Fill missing values (like na.fill in R, or tidyr::replace_na)
df_filled = df.fillna(0)
print(df_filled)
```
```
    name   age   salary
0  Alice  25.0  50000.0
1    Bob   0.0  60000.0
2      0  35.0  75000.0
3  David  28.0      0.0
```

```python
# Fill with mean (column-specific)
df['age'].fillna(df['age'].mean(), inplace=True)
print(df)
```
```
    name        age   salary
0  Alice  25.000000  50000.0
1    Bob  29.333333  60000.0
2   None  35.000000  75000.0
3  David  28.000000      NaN
```

```python
# Fill with forward fill (like na.locf in zoo)
df_ffill = df.fillna(method='ffill')

# Fill with backward fill
df_bfill = df.fillna(method='bfill')
```

### Wrong Format

```python
# Convert to datetime (like as.Date() in R)
data = {
    'date': ['2024-01-01', '2024-01-02', '20240103'],
    'value': [10, 20, 30]
}
df = pd.DataFrame(data)

# Convert column to datetime
df['date'] = pd.to_datetime(df['date'], format='mixed')
print(df.dtypes)
```
```
date     datetime64[ns]
value             int64
dtype: object
```

```python
# Remove rows with wrong format
df.dropna(subset=['date'], inplace=True)

# Convert numeric columns
df['value'] = pd.to_numeric(df['value'], errors='coerce')
```

### Wrong Data

```python
# Create DataFrame with outliers
data = {
    'age': [25, 30, 35, 200, 28]  # 200 is likely wrong
}
df = pd.DataFrame(data)

# Identify outliers using conditions
print(df[df['age'] > 100])
```
```
   age
3  200
```

```python
# Replace wrong values
df.loc[df['age'] > 100, 'age'] = df['age'].median()
print(df)
```
```
   age
0   25
1   30
2   35
3   30
4   28
```

```python
# Remove rows with wrong data
df = df[df['age'] <= 100]
```

### Duplicates

```python
# Create DataFrame with duplicates
data = {
    'name': ['Alice', 'Bob', 'Alice', 'David'],
    'age': [25, 30, 25, 28]
}
df = pd.DataFrame(data)

# Check for duplicates (like duplicated() in R)
print(df.duplicated())
```
```
0    False
1    False
2     True
3    False
dtype: bool
```

```python
# Remove duplicates (like unique() or distinct() in dplyr)
df_unique = df.drop_duplicates()
print(df_unique)
```
```
    name  age
0  Alice   25
1    Bob   30
3  David   28
```

```python
# Remove duplicates based on specific columns
df_unique = df.drop_duplicates(subset=['name'])
print(df_unique)
```
```
    name  age
0  Alice   25
1    Bob   30
3  David   28
```

---

## Correlations

```python
# Create DataFrame with numeric data
data = {
    'A': [1, 2, 3, 4, 5],
    'B': [2, 4, 6, 8, 10],
    'C': [5, 4, 3, 2, 1]
}
df = pd.DataFrame(data)

# Correlation matrix (like cor() in R)
print(df.corr())
```
```
     A    B    C
A  1.0  1.0 -1.0
B  1.0  1.0 -1.0
C -1.0 -1.0  1.0
```

```python
# Correlation with specific method
# Pearson (default)
print(df.corr(method='pearson'))

# Spearman rank correlation
print(df.corr(method='spearman'))

# Kendall Tau correlation
print(df.corr(method='kendall'))
```
```
     A    B    C
A  1.0  1.0 -1.0
B  1.0  1.0 -1.0
C -1.0 -1.0  1.0
```

```python
# Correlation between two columns
print(df['A'].corr(df['B']))
```
```
1.0
```

```python
# Covariance matrix (like cov() in R)
print(df.cov())
```
```
     A     B    C
A  2.5   5.0 -2.5
B  5.0  10.0 -5.0
C -2.5  -5.0  2.5
```

---

## Plotting

Pandas uses matplotlib for plotting (similar to base plot or ggplot2 in R).

```python
import matplotlib.pyplot as plt

# Create sample data
data = {
    'month': ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
    'sales': [100, 120, 140, 110, 150]
}
df = pd.DataFrame(data)

# Line plot (like plot() in R)
df.plot(x='month', y='sales', kind='line')
plt.title('Monthly Sales')
plt.show()
```

```python
# Bar plot (like barplot() in R)
df.plot(x='month', y='sales', kind='bar')
plt.title('Sales by Month')
plt.show()
```

```python
# Horizontal bar plot
df.plot(x='month', y='sales', kind='barh')
plt.show()
```

```python
# Histogram (like hist() in R)
data = {'values': np.random.randn(100)}
df = pd.DataFrame(data)

df['values'].plot(kind='hist', bins=20)
plt.title('Distribution')
plt.show()
```

```python
# Scatter plot (like plot(x, y) in R)
data = {
    'x': [1, 2, 3, 4, 5],
    'y': [2, 4, 5, 4, 6]
}
df = pd.DataFrame(data)

df.plot(x='x', y='y', kind='scatter')
plt.title('Scatter Plot')
plt.show()
```

```python
# Box plot (like boxplot() in R)
data = {
    'A': np.random.randn(50),
    'B': np.random.randn(50) + 1,
    'C': np.random.randn(50) - 1
}
df = pd.DataFrame(data)

df.plot(kind='box')
plt.title('Box Plot')
plt.show()
```

```python
# Multiple columns on same plot
data = {
    'month': ['Jan', 'Feb', 'Mar', 'Apr'],
    'sales': [100, 120, 140, 110],
    'costs': [60, 70, 80, 65]
}
df = pd.DataFrame(data)

df.plot(x='month', y=['sales', 'costs'], kind='line')
plt.title('Sales vs Costs')
plt.legend()
plt.show()
```

```python
# Customize plot
ax = df.plot(x='month', y='sales', 
             kind='line',
             color='blue',
             linestyle='--',
             marker='o',
             figsize=(10, 6))
ax.set_xlabel('Month')
ax.set_ylabel('Sales ($)')
ax.set_title('Monthly Sales Trend')
plt.grid(True)
plt.show()
```

```python
# Subplots (like par(mfrow) in R)
fig, axes = plt.subplots(2, 2, figsize=(10, 8))

df['sales'].plot(kind='line', ax=axes[0, 0], title='Line')
df['sales'].plot(kind='bar', ax=axes[0, 1], title='Bar')
df['sales'].plot(kind='hist', ax=axes[1, 0], title='Histogram')
df['sales'].plot(kind='box', ax=axes[1, 1], title='Box')

plt.tight_layout()
plt.show()
```

### Quick Plotting Tips

```python
# Save plot to file
df.plot(x='month', y='sales')
plt.savefig('sales_plot.png', dpi=300, bbox_inches='tight')

# Style options (similar to ggplot themes)
plt.style.use('ggplot')
df.plot(x='month', y='sales')
plt.show()

# Available styles
print(plt.style.available)
```
```
['Solarize_Light2', '_classic_test_patch', '_mpl-gallery', '_mpl-gallery-nogrid', 
 'bmh', 'classic', 'dark_background', 'fast', 'fivethirtyeight', 'ggplot', 
 'grayscale', 'seaborn-v0_8', 'seaborn-v0_8-bright', 'seaborn-v0_8-colorblind', 
 'seaborn-v0_8-dark', 'seaborn-v0_8-dark-palette', 'seaborn-v0_8-darkgrid', 
 'seaborn-v0_8-deep', 'seaborn-v0_8-muted', 'seaborn-v0_8-notebook', 
 'seaborn-v0_8-paper', 'seaborn-v0_8-pastel', 'seaborn-v0_8-poster', 
 'seaborn-v0_8-talk', 'seaborn-v0_8-ticks', 'seaborn-v0_8-white', 
 'seaborn-v0_8-whitegrid', 'tableau-colorblind10']
```

---

## Common DataFrame Operations (R Comparison)

```python
# Subsetting (like df[df$age > 30, ] in R)
df_subset = df[df['age'] > 30]

# Select columns (like select() in dplyr)
df_subset = df[['name', 'age']]

# Filter and select (like filter() %>% select() in dplyr)
df_subset = df[df['age'] > 30][['name', 'age']]

# Sort (like arrange() in dplyr or order() in base R)
df_sorted = df.sort_values('age', ascending=False)

# Group by and aggregate (like group_by() %>% summarize() in dplyr)
grouped = df.groupby('category').agg({
    'sales': 'sum',
    'age': 'mean'
})

# Add new column (like mutate() in dplyr)
df['age_squared'] = df['age'] ** 2

# Rename columns (like rename() in dplyr)
df_renamed = df.rename(columns={'age': 'years', 'name': 'person'})

# Join DataFrames (like merge() or left_join() in dplyr)
df_merged = pd.merge(df1, df2, on='id', how='left')
# how options: 'left', 'right', 'outer', 'inner'
```

---

## Quick Reference

| Pandas | R (base) | R (tidyverse) |
|--------|----------|---------------|
| `pd.read_csv()` | `read.csv()` | `readr::read_csv()` |
| `df.head()` | `head()` | `head()` |
| `df.describe()` | `summary()` | `skimr::skim()` |
| `df[df['x'] > 5]` | `df[df$x > 5, ]` | `filter(df, x > 5)` |
| `df[['col1', 'col2']]` | `df[, c('col1', 'col2')]` | `select(df, col1, col2)` |
| `df.sort_values('x')` | `df[order(df$x), ]` | `arrange(df, x)` |
| `df.groupby('x').mean()` | `aggregate()` | `group_by() %>% summarize()` |
| `df.dropna()` | `na.omit()` | `drop_na()` |
| `df.fillna(value)` | `replace(df, is.na(df), value)` | `replace_na()` |
| `df.corr()` | `cor()` | `cor()` |
| `df.plot()` | `plot()` | `ggplot() + geom_*()` |

---
