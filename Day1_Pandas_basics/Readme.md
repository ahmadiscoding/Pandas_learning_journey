# 🐼 Day 1 — Pandas Foundations

Day 1 focused on understanding the core building blocks of Pandas:
Series (1D data) and DataFrame (2D data).

---

# 🧠 What I Learned

## 🔹 1. Pandas Series

A Series is a one-dimensional labeled array.

### Key Points:
- Works like a single column
- Has index (labels) + values
- Built on NumPy
- Supports vectorized operations

---

### 🔸 Creating Series

# import pandas as pd  
# import numpy as np  

# From list  
# s1 = pd.Series([10, 20, 30])  

# From dictionary  
# s2 = pd.Series({'Ali': 90, 'Sara': 95})  

# With custom index  
# s3 = pd.Series([100, 200, 300], index=['A','B','C'])  

---

### 🔸 Indexing

# s1[0]  
# s3['A']  

---

### 🔸 Operations

# s1 * 2  

---

### 🔸 Automatic Alignment (Very Important)

Pandas aligns data using index labels, not position.

# s1 = pd.Series([10,20,30], index=['a','b','c'])  
# s2 = pd.Series([50,60,70], index=['b','c','d'])  

# s1 + s2  

Explanation:
- Only matching indexes are added
- Non-matching values become NaN

Fix:

# s1.add(s2, fill_value=0)  

---

## 🔹 2. Pandas DataFrame

A DataFrame is a two-dimensional table.

### Key Points:
- Rows + Columns
- Each column is a Series
- Can store different data types

---

### 🔸 Creating DataFrame

# data = {  
#     'Name': ['Ali', 'Sara', 'Zain'],  
#     'Age': [20, 21, 19],  
#     'City': ['Lahore', 'Karachi', 'Islamabad']  
# }  

# df = pd.DataFrame(data)  

---

### 🔸 Structure

# df.shape  
# df.columns  
# df.index  
# df.dtypes  

---

### 🔸 Viewing Data

# df.head()  
# df.tail()  
# df.sample(2)  

---

### 🔸 Data Information

# df.info()  
# df.describe()  

---

### 🔸 Selecting Data

Columns:

# df['Name']  
# df[['Name', 'City']]  

Rows:

# df.loc[0]  
# df.iloc[0]  

Specific value:

# df.loc[0, 'Name']  

---

### 🔸 Filtering Data

# df[df['Age'] > 20]  

Multiple conditions:

# df[(df['Age'] > 20) & (df['City'] == 'Karachi')]  

Using list filtering:

# df[df['City'].isin(['Lahore','Karachi'])]  

---

### 🔸 Adding / Modifying Columns

# df['Salary'] = [50000, 60000, 55000]  

# df['Age'] = df['Age'] + 1  

---

### 🔸 Sorting

# df.sort_values(by='Age')  
# df.sort_values(by='Age', ascending=False)  

---

### 🔸 Missing Values

# df.isnull()  
# df.isnull().sum()  

Handling:

# df.fillna(0)  
# df.dropna()  

---

### 🔸 GroupBy

# df.groupby('City')['Age'].mean()  

Used to analyze grouped data.

---

# 🧪 Practice Work

- Created Series using multiple methods  
- Practiced indexing and operations  
- Created DataFrame  
- Applied filtering and sorting  

---

# 🎬 Mini Project — Movies Dataset

Dataset Columns:
- Title
- Year
- Rating
- Genre

Tasks:
- Created DataFrame  
- Used describe()  
- Used value_counts()  
- Exported dataset  

# movies.to_csv("movies.csv", index=False)  

---

# 📁 Files in this Folder

- day1_Series.ipynb  
- day1_dataframes.ipynb  
- day1_practice.ipynb  
- miniproject.ipynb  
- Titanic-Dataset.csv  

---

# 🧠 Key Takeaways

- Pandas uses labels instead of position  
- Series = 1D data  
- DataFrame = 2D data  
- Automatic alignment is a core concept  
- DataFrames are used in real-world datasets  

---

# 🚀 Next Step

Day 2 → Data Loading + Exploratory Data Analysis (EDA)