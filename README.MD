In Python (and many other programming languages), **attributes** and **functions** (or methods) are both used to interact with objects, but they serve different purposes.

---

### 🧩 **Attribute**
- An **attribute** is a **value or property** associated with an object.
- It **does not require parentheses** to access.
- It usually represents **data** or **state**.

#### ✅ Example:
```python
import pandas as pd

df = pd.DataFrame({'A': [1, 2, 3]})

# 'columns' is an attribute
print(df.columns)
```
Here, `df.columns` gives you the column names of the DataFrame. No parentheses needed.

---

### ⚙️ **Function (Method)**
- A **function** (or method when attached to an object) is a **block of code** that performs an **action**.
- It **requires parentheses** to call, even if there are no arguments.
- It usually **does something** with the object.

#### ✅ Example:
```python
# 'head()' is a function
print(df.head())
```
Here, `df.head()` returns the first few rows of the DataFrame. Parentheses are required.

---

### 🔍 Summary Table

| Feature      | Attribute            | Function (Method)       |
|--------------|----------------------|--------------------------|
| Purpose      | Stores data/state    | Performs an action       |
| Syntax       | `object.attribute`   | `object.function()`      |
| Parentheses  | ❌ Not used           | ✅ Required               |
| Example      | `df.columns`         | `df.head()`              |

---

Here’s a **detailed explanation and comparison** of the four fundamental Python data structures: **List**, **Dictionary (dict)**, **Set**, and **Tuple**.

---

## 🧾 1. **List**

### ✅ Characteristics:
- **Ordered**: Elements maintain the order in which they were added.
- **Mutable**: You can change, add, or remove elements.
- **Allows duplicates**: Same value can appear multiple times.
- **Indexable**: Access elements by position using indices.

### 🧪 Example:
```python
my_list = [1, 2, 3, 2]
print(my_list[1])  # Output: 2
```

### 📌 Use Case:
Use a list when you need an ordered collection of items that may change over time.

---

## 📘 2. **Dictionary (`dict`)**

### ✅ Characteristics:
- **Key-value pairs**: Each item is a pair of a key and a value.
- **Keys are unique**: No duplicate keys allowed.
- **Mutable**: You can add, update, or delete key-value pairs.
- **Ordered** (since Python 3.7+): Maintains insertion order.

### 🧪 Example:
```python
my_dict = {"name": "Alice", "age": 25}
print(my_dict["name"])  # Output: Alice
```

### 📌 Use Case:
Use a dictionary when you need to associate values with unique keys (like a mini-database).

---

## 🔢 3. **Set**

### ✅ Characteristics:
- **Unordered**: No guaranteed order of elements.
- **Mutable**: You can add or remove elements.
- **No duplicates**: Automatically removes duplicate values.
- **Not indexable**: You can't access elements by position.

### 🧪 Example:
```python
my_set = {1, 2, 3, 2}
print(my_set)  # Output: {1, 2, 3}
```

### 📌 Use Case:
Use a set when you need to store **unique** items and don’t care about order.

---

## 📦 4. **Tuple**

### ✅ Characteristics:
- **Ordered**: Elements maintain their order.
- **Immutable**: Cannot be changed after creation.
- **Allows duplicates**: Same value can appear more than once.
- **Indexable**: Access elements by position.

### 🧪 Example:
```python
my_tuple = (1, 2, 3)
print(my_tuple[0])  # Output: 1
```

### 📌 Use Case:
Use a tuple when you need a fixed, ordered collection of items that shouldn’t change.

---

## 🔍 Summary Table

| Feature         | List        | Dict               | Set         | Tuple       |
|------------------|-------------|--------------------|-------------|-------------|
| Ordered          | ✅          | ✅ (since 3.7)      | ❌          | ✅          |
| Mutable          | ✅          | ✅                 | ✅          | ❌          |
| Allows Duplicates| ✅          | ❌ (keys only)      | ❌          | ✅          |
| Indexable        | ✅          | By key             | ❌          | ✅          |
| Syntax           | `[1, 2]`    | `{'a': 1}`          | `{1, 2}`     | `(1, 2)`    |

---
Great question! Let's break down the difference between **ordered** and **unordered** collections in Python:

---

### 📚 **Ordered Collection**

An **ordered** collection means that the **items have a defined sequence**, and this order is **preserved** when you access or iterate over the collection.

#### ✅ Examples:
- **List**: `[10, 20, 30]`
- **Tuple**: `(10, 20, 30)`
- **Dict** (since Python 3.7+): `{"a": 1, "b": 2}`

#### 🔍 Behavior:
```python
my_list = [10, 20, 30]
print(my_list[0])  # Output: 10
```
You can access elements by their **position** (index), and the order stays the same.

---

### 📚 **Unordered Collection**

An **unordered** collection means that the **items do not have a fixed position**. The order in which you insert items is **not guaranteed** to be preserved.

#### ✅ Example:
- **Set**: `{10, 20, 30}`

#### 🔍 Behavior:
```python
my_set = {10, 20, 30}
for item in my_set:
    print(item)
```
The output order may vary each time you run the code.

---

### 🧠 Analogy

- **Ordered**: Like a **queue** at a movie theater — people stay in line in the order they arrived.
- **Unordered**: Like a **crowd** at a concert — people are there, but not in any specific order.

---
Absolutely! Let's break down **dynamic memory allocation in Python** in a simple and clear way.

---

## 🧠 What is Dynamic Memory Allocation?

**Dynamic memory allocation** means that memory is allocated to variables **at runtime**, not in advance. Python handles this **automatically** behind the scenes.

---

## 🧰 How It Works in Python

### 1. **Automatic Allocation**
When you create a variable in Python:

```python
x = 10
```

- Python automatically allocates memory for the integer `10`.
- You don’t need to declare the type or size of the variable.
- The memory is managed by Python’s **memory manager**.

---

### 2. **Reference Counting**
Python uses **reference counting** to keep track of how many variables refer to a value.

```python
a = [1, 2, 3]
b = a  # Both a and b refer to the same list
```

- The list `[1, 2, 3]` has a reference count of 2.
- When no variables refer to it, Python **automatically frees** the memory (garbage collection).

---

### 3. **Garbage Collection**
Python has a built-in **garbage collector** that reclaims memory from objects that are no longer in use.

```python
import gc
gc.collect()  # Manually trigger garbage collection (optional)
```

---

### 4. **Memory for Containers**
For structures like lists, dictionaries, and sets:
- Python **dynamically resizes** them as needed.
- For example, a list grows in chunks to reduce the number of memory operations.

---

## 📦 Summary

| Feature                  | Python Behavior                          |
|--------------------------|-------------------------------------------|
| Memory allocation        | Automatic at runtime                      |
| Type declaration         | Not required                              |
| Memory resizing          | Handled internally (e.g., for lists)      |
| Memory deallocation      | Done via garbage collection               |
| Manual memory control    | Not needed (unlike C/C++)                 |

---

In Python, the **Garbage Collector (GC)** is a built-in system that **automatically manages memory** by cleaning up objects that are no longer needed. This helps prevent memory leaks and keeps your program efficient.

---

## 🧹 What is Garbage Collection?

Garbage collection is the process of:
- **Identifying** objects that are no longer in use.
- **Reclaiming** the memory they occupy.
- **Freeing** it for future use.

---

## 🔄 How It Works in Python

Python primarily uses **reference counting** and a **cyclic garbage collector**:

### 1. **Reference Counting**
Every object keeps track of how many references point to it.

```python
a = [1, 2, 3]
b = a  # Reference count is 2
del a  # Reference count is 1
del b  # Reference count is 0 → object is deleted
```

When the count reaches **zero**, the object is **immediately destroyed**.

---

### 2. **Cyclic Garbage Collector**
Sometimes, objects reference each other in a **cycle**, like:

```python
a = {}
b = {'ref': a}
a['ref'] = b
```

Even if you `del a` and `del b`, the cycle keeps them alive. Python’s **cyclic GC** detects and removes these.

---

## 🛠️ Using the `gc` Module

You can interact with the garbage collector using the `gc` module:

```python
import gc

gc.collect()  # Manually trigger garbage collection
print(gc.get_stats())  # View GC stats
```

---

## 📦 Summary

| Feature                  | Description                                      |
|--------------------------|--------------------------------------------------|
| Automatic                | Yes, Python handles it for you                   |
| Manual control           | Optional via `gc` module                         |
| Reference counting       | Primary mechanism                               |
| Cyclic GC                | Handles reference cycles                         |
| Benefit                  | Prevents memory leaks, improves performance      |

---

In Python, a **programming paradigm** refers to a style or way of programming. Python is a **multi-paradigm language**, which means it supports several programming approaches. Here's a breakdown of the main paradigms Python supports:

---

## 🧱 1. **Procedural Programming**
- **Focus**: Step-by-step instructions (like a recipe).
- **Structure**: Uses functions, loops, and conditionals.
- **Common in**: Scripts, automation, small programs.

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")
```

---

## 🧠 2. **Object-Oriented Programming (OOP)**
- **Focus**: Objects that contain both data and behavior.
- **Structure**: Uses classes and objects.
- **Common in**: Large applications, GUI apps, games.

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        print(f"Hello, I'm {self.name}")

p = Person("Bob")
p.greet()
```

---

## 🧮 3. **Functional Programming**
- **Focus**: Pure functions, immutability, and avoiding side effects.
- **Structure**: Uses `map()`, `filter()`, `lambda`, and recursion.
- **Common in**: Data processing, mathematical computations.

```python
nums = [1, 2, 3, 4]
squares = list(map(lambda x: x**2, nums))
print(squares)
```

---

## 🔁 4. **Imperative Programming**
- **Focus**: How to perform tasks (explicit control flow).
- **Structure**: Uses statements that change a program’s state.
- **Common in**: Most Python code (overlaps with procedural).

```python
x = 10
x += 5
print(x)
```

---

## 🧪 5. **Declarative Programming** (limited support)
- **Focus**: What to do, not how to do it.
- **Examples**: SQL-like queries in libraries like `pandas`.

```python
import pandas as pd

df = pd.DataFrame({'age': [25, 30, 35]})
print(df[df['age'] > 30])
```

---

## 🧭 Summary Table

| Paradigm            | Description                              | Python Support |
|---------------------|------------------------------------------|----------------|
| Procedural          | Step-by-step instructions                | ✅              |
| Object-Oriented     | Classes and objects                      | ✅              |
| Functional          | Pure functions, immutability             | ✅              |
| Imperative          | Explicit control flow                    | ✅              |
| Declarative         | Describe what, not how                   | ⚠️ (limited)    |

---
Here's a **complete set of notes** for working with Excel and CSV files in Python using **Pandas**, including reading files, viewing data, sorting, and handling null values.

---

## 📘 **1. Reading Excel and CSV Files**

```python
import pandas as pd

# Reading a CSV file
df_csv = pd.read_csv('your_file.csv')

# Reading an Excel file
df_excel = pd.read_excel('your_file.xlsx', engine='openpyxl')
```

> Replace `'your_file.csv'` and `'your_file.xlsx'` with your actual file paths.

---

## 👀 **2. Viewing Data with `head()` and `tail()`**

```python
# First 5 rows
print(df_csv.head())

# Last 5 rows
print(df_excel.tail())
```

You can also pass a number to see more or fewer rows:
```python
df_csv.head(10)  # First 10 rows
df_excel.tail(3)  # Last 3 rows
```

---

## 🔃 **3. Sorting Data**

```python
# Sort in ascending order by a column
df_sorted_asc = df_csv.sort_values(by='column_name', ascending=True)

# Sort in descending order
df_sorted_desc = df_excel.sort_values(by='column_name', ascending=False)
```

> Replace `'column_name'` with the actual column you want to sort by.

---

## 🚫 **4. Handling Null (Missing) Values**

### 🔍 Detecting Nulls
```python
print(df_csv.isnull().sum())  # Count of nulls per column
```

### 🧹 Removing Nulls
```python
df_cleaned = df_csv.dropna()  # Removes rows with any null values
```

### 🧪 Replacing Nulls
```python
df_filled = df_excel.fillna(value='N/A')  # Replace nulls with 'N/A'
```

---

## 🧠 Summary

| Task                  | Function                  |
|-----------------------|---------------------------|
| Read CSV              | `pd.read_csv()`           |
| Read Excel            | `pd.read_excel()`         |
| View top rows         | `df.head()`               |
| View bottom rows      | `df.tail()`               |
| Sort data             | `df.sort_values()`        |
| Detect nulls          | `df.isnull().sum()`       |
| Drop nulls            | `df.dropna()`             |
| Fill nulls            | `df.fillna()`             |

---

# FastAPI SQL Server Example

This project demonstrates how to build a simple **FastAPI** application that connects to a SQL Server database using `pyodbc` and exposes an endpoint to fetch all rows from a table.

---

## Features

- Connects to SQL Server using `pyodbc`
- Exposes a REST API endpoint (`/asd`) to fetch all rows from the `asD` table
- Returns results as JSON

---

## Prerequisites

- Python 3.7+
- SQL Server (local or remote)
- [ODBC Driver for SQL Server](https://learn.microsoft.com/en-us/sql/connect/odbc/download-odbc-driver-for-sql-server) (e.g., ODBC Driver 17 for SQL Server)
- Python packages: `fastapi`, `uvicorn`, `pyodbc`

---

## Installation

1. **Install Python dependencies:**
    ```
    pip install fastapi uvicorn pyodbc
    ```

2. **Install the ODBC Driver for SQL Server:**
    - [Download from Microsoft](https://learn.microsoft.com/en-us/sql/connect/odbc/download-odbc-driver-for-sql-server)
    - Make sure the driver name matches what you use in your connection string (see below).

---

## Usage

1. **Update the database connection details in your Python script:**

    ```python
    def get_connection():
        conn_str = (
            "DRIVER={ODBC Driver 17 for SQL Server};"
            "SERVER=localhost;"
            "DATABASE=YourDatabaseName;"
            "UID=YourUsername;"
            "PWD=YourPassword;"
        )
        return pyodbc.connect(conn_str)
    ```
    - Replace `ODBC Driver 17 for SQL Server` with your installed driver (check with `pyodbc.drivers()`).
    - Replace `YourDatabaseName`, `YourUsername`, and `YourPassword` with your actual credentials.

2. **Ensure your table exists:**

    ```sql
    CREATE TABLE asD (
        id INT PRIMARY KEY,
        name NVARCHAR(100),
        email NVARCHAR(100)
    );
    ```

3. **Run the FastAPI app:**
    ```
    uvicorn app:app --reload
    ```
    - `app` is the filename (without `.py`), and the second `app` is the FastAPI instance.

4. **Access the API:**
    - Open your browser or API client and go to: [http://localhost:8000/asd](http://localhost:8000/asd)
    - You can also view the interactive docs at: [http://localhost:8000/docs](http://localhost:8000/docs)

---

## Example Endpoint

- **GET** `/asd`  
  Returns all rows from the `asD` table as a JSON array.

---

## Troubleshooting

- **ODBC Driver errors:**  
  Make sure the driver name in your connection string matches what is installed. Check with:
    ```python
    import pyodbc
    print(pyodbc.drivers())
    ```
- **404 Not Found:**  
  Make sure you are visiting the correct endpoint (`/asd`) and that the server is running.
- **500 Internal Server Error:**  
  Check your database credentials, table existence, and server status.

---

