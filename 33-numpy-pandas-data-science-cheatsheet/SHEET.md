# 🐍 Module 33: NumPy & Pandas Data Science Master Sheet (30 Formulas)

Complete reference for 30 essential NumPy and Pandas operations, array manipulations, data filtering, aggregations, and cleaning code snippets categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner NumPy & Pandas Operations (1 - 10)

```python
import numpy as np
import pandas as pd

# 1. Create 1D and 2D NumPy Arrays
arr1d = np.array([1, 2, 3, 4, 5])
arr2d = np.array([[1, 2, 3], [4, 5, 6]])

# 2. Create Array of Zeros, Ones, or Linearly Spaced Numbers
zeros = np.zeros((3, 3))
ones = np.ones((2, 4))
linspace = np.linspace(0, 10, 5)

# 3. Read CSV File into Pandas DataFrame
df = pd.read_csv('data.csv')

# 4. View First 5 Rows of DataFrame
df.head()

# 5. View DataFrame Summary Statistics & Data Types
df.info()
df.describe()

# 6. Check Shape (Rows, Columns) of DataFrame
df.shape

# 7. Select Single Column or Multiple Columns
col = df['age']
sub_df = df[['name', 'age', 'salary']]

# 8. Filter Rows Based on Condition
adults = df[df['age'] >= 18]

# 9. Count Unique Values in a Series
df['category'].value_counts()

# 10. Check Missing / Null Values Count
df.isnull().sum()
```

---

## 🟡 Level 2: Medium / Intermediate Data Processing & Transformations (11 - 20)

```python
# 11. NumPy Array Reshaping & Transpose
reshaped = arr1d.reshape(5, 1)
transposed = arr2d.T

# 12. NumPy Matrix Multiplication (Dot Product)
matrix_product = np.dot(arr2d, arr2d.T)

# 13. Label / Index Selection using .loc[] (By Label)
row = df.loc[0, 'name']
filtered = df.loc[df['salary'] > 50000, ['name', 'salary']]

# 14. Positional Selection using .iloc[] (By Index Integer)
subset = df.iloc[0:10, 0:3]

# 15. Fill Missing Null Values with Mean / Median
df['age'].fillna(df['age'].mean(), inplace=True)

# 16. Drop Rows with Missing Null Values
df_clean = df.dropna(subset=['email'])

# 17. GroupBy Aggregation (Average Salary by Department)
dept_summary = df.groupby('department')['salary'].mean()

# 18. Multi-Column GroupBy Aggregation (Mean & Count)
dept_stats = df.groupby('department').agg({'salary': ['mean', 'max'], 'id': 'count'})

# 19. Merge / Join Two DataFrames on Key Column
merged_df = pd.merge(df1, df2, on='user_id', how='inner')

# 20. Concatenate DataFrames Vertically or Horizontally
combined = pd.concat([df1, df2], axis=0)  # axis=0 (rows), axis=1 (cols)
```

---

## 🔴 Level 3: Hard / Advanced Feature Engineering & Exporting (21 - 30)

```python
# 21. Apply Custom Function to Column (lambda)
df['tax'] = df['salary'].apply(lambda x: x * 0.18)

# 22. One-Hot Encoding Categorical Variables
df_encoded = pd.get_dummies(df, columns=['gender', 'city'])

# 23. Pivot Table Creation
pivot = df.pivot_table(index='department', columns='gender', values='salary', aggfunc='mean')

# 24. Sort DataFrame by Column Values
df_sorted = df.sort_values(by='salary', ascending=False)

# 25. Remove Duplicate Rows
df_unique = df.drop_duplicates(subset=['email'])

# 26. String Operations on Series (.str)
df['email_domain'] = df['email'].str.split('@').str[1]

# 27. NumPy Vectorized Conditional (np.where)
df['status'] = np.where(df['score'] >= 70, 'Pass', 'Fail')

# 28. Calculate Correlation Matrix across Numeric Columns
corr_matrix = df.corr(numeric_only=True)

# 29. Export Processed DataFrame to CSV File
df.to_csv('cleaned_data.csv', index=False)

# 30. Export Processed DataFrame to Excel File
df.to_excel('output.xlsx', sheet_name='Sheet1', index=False)
```
