### **📌 Pandas DataFrame Cheatsheet**  

Here’s a **concise** and **structured** table of the **most commonly used Pandas DataFrame functions** for **reading, writing, cleaning, filtering, and analyzing data.**  

---

### 🔹 **1. Creating & Loading DataFrames**
| **Function** | **Description** | **Example Usage** |
|-------------|----------------|------------------|
| `pd.read_csv(filepath)` | Load a CSV file into a DataFrame | `df = pd.read_csv("data.csv")` |
| `pd.read_excel(filepath, sheet_name=0)` | Load an Excel file | `df = pd.read_excel("data.xlsx")` |
| `pd.DataFrame(data, columns=[...])` | Create a DataFrame from a dict/list | `df = pd.DataFrame({'A': [1,2,3]})` |
| `df.to_csv(filepath, index=False)` | Save DataFrame to a CSV file | `df.to_csv("output.csv", index=False)` |
| `df.to_excel(filepath, index=False)` | Save DataFrame to an Excel file | `df.to_excel("output.xlsx", index=False)` |

---

### 🔹 **2. Exploring Data**
| **Function** | **Description** | **Example Usage** |
|-------------|----------------|------------------|
| `df.head(n)` | View first `n` rows | `df.head(5)` |
| `df.tail(n)` | View last `n` rows | `df.tail(3)` |
| `df.shape` | Get number of rows & columns | `(rows, cols) = df.shape` |
| `df.info()` | Summary of DataFrame | `df.info()` |
| `df.describe()` | Summary statistics (numerical columns) | `df.describe()` |
| `df.columns` | List column names | `df.columns` |
| `df.dtypes` | Show data types of columns | `df.dtypes` |

---

### 🔹 **3. Selecting & Filtering Data**
| **Function** | **Description** | **Example Usage** |
|-------------|----------------|------------------|
| `df['column']` | Select single column | `df['Price']` |
| `df[['col1', 'col2']]` | Select multiple columns | `df[['Name', 'Salary']]` |
| `df.iloc[row, col]` | Select by index position | `df.iloc[0, 1]` |
| `df.loc[row, col]` | Select by label | `df.loc[0, 'Salary']` |
| `df[df['col'] > value]` | Filter rows | `df[df['Age'] > 30]` |
| `df[(df['col1'] > 10) & (df['col2'] == 'Yes')]` | Multiple conditions | `df[(df['Salary'] > 50000) & (df['Status'] == 'Employed')]` |
| `df.query("col1 > 10 and col2 == 'Yes'")` | Query with string conditions | `df.query("Salary > 50000 and Status == 'Employed'")` |

---

### 🔹 **4. Handling Missing Data**
| **Function** | **Description** | **Example Usage** |
|-------------|----------------|------------------|
| `df.isnull().sum()` | Count missing values per column | `df.isnull().sum()` |
| `df.dropna()` | Remove rows with missing values | `df.dropna()` |
| `df.fillna(value)` | Fill missing values | `df.fillna(0)` |
| `df['col'].fillna(df['col'].mean())` | Fill with column mean | `df['Age'].fillna(df['Age'].mean())` |

---

### 🔹 **5. Modifying Data**
| **Function** | **Description** | **Example Usage** |
|-------------|----------------|------------------|
| `df['col'].astype(type)` | Convert data type | `df['Salary'] = df['Salary'].astype(int)` |
| `df.rename(columns={'old': 'new'})` | Rename columns | `df.rename(columns={'Age': 'Years'})` |
| `df.drop(columns=['col1', 'col2'])` | Remove columns | `df.drop(columns=['ID'])` |
| `df['col1'] + df['col2']` | Add two columns | `df['Total'] = df['Price'] * df['Quantity']` |
| `df.assign(NewCol=lambda x: x['col'] * 2)` | Add a new column using a function | `df.assign(SalaryDoubled=lambda x: x['Salary'] * 2)` |
| `df.sort_values(by='col', ascending=False)` | Sort DataFrame | `df.sort_values(by='Salary', ascending=False)` |

---

### 🔹 **6. Grouping & Aggregation**
| **Function** | **Description** | **Example Usage** |
|-------------|----------------|------------------|
| `df.groupby('col').sum()` | Group by column and sum | `df.groupby('Department')['Salary'].sum()` |
| `df.groupby('col').mean()` | Group by and calculate mean | `df.groupby('Category')['Price'].mean()` |
| `df.pivot(index='col1', columns='col2', values='col3')` | Pivot table | `df.pivot(index='Year', columns='Category', values='Sales')` |

---

### 🔹 **7. Merging & Joining DataFrames**
| **Function** | **Description** | **Example Usage** |
|-------------|----------------|------------------|
| `df1.merge(df2, on='col', how='inner')` | Merge two DataFrames | `df1.merge(df2, on='ID', how='inner')` |
| `pd.concat([df1, df2])` | Concatenate DataFrames | `pd.concat([df1, df2], axis=0)` |

---

### 🔹 **8. Applying Functions**
| **Function** | **Description** | **Example Usage** |
|-------------|----------------|------------------|
| `df['col'].apply(func)` | Apply function to column | `df['Salary'].apply(lambda x: x * 1.1)` |
| `df.applymap(func)` | Apply function to all elements | `df.applymap(lambda x: x.upper() if isinstance(x, str) else x)` |

---

### 🔹 **9. Exporting Data**
| **Function** | **Description** | **Example Usage** |
|-------------|----------------|------------------|
| `df.to_csv(filepath, index=False)` | Save as CSV | `df.to_csv("output.csv", index=False)` |
| `df.to_excel(filepath)` | Save as Excel | `df.to_excel("output.xlsx")` |

---

This should cover **everything you need** to **clean, manipulate, and analyze tables** in Pandas! 🚀 Let me know if you need **examples or deeper explanations** on any function! 🔥
