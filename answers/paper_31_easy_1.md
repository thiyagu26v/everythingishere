# 📝 Question Paper 31 — Easy 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is a variable in Python? How do you assign a value to one?
2. What is Django? Why is it called a "batteries-included" framework?
3. What is the difference between `INT` and `FLOAT` data types in SQL?
4. What is a tuple in Python? How is it different from a list?
5. What is an API endpoint? Give a simple example.
6. What are loops in Python? What is the difference between `for` and `while`?
7. What does `SELECT *` mean in SQL?
8. What is `models.py` used for in a Django app?
9. What is the difference between `append()` and `extend()` in Python lists?
10. What is a database? Name two popular relational databases.

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python built-in function returns the smallest item in a list?
2. What SQL keyword filters rows based on a condition?
3. What Django command starts a development server?
4. What Python function converts a string to an integer?
5. What HTTP method retrieves data from a server?
6. What Python method adds an element to the end of a list?
7. What SQL keyword orders results from lowest to highest?
8. What file type does DRF return by default?
9. What Python operator is used for exponentiation?
10. What does `HTTP` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of numbers and returns a list of only even numbers.
```
Input:  [1, 2, 3, 4, 5, 6, 7, 8]
Output: [2, 4, 6, 8]
```

**Problem 2:** Write a function that counts how many times each character appears in a string (ignore spaces).
```
Input:  "hello world"
Output: {"h": 1, "e": 1, "l": 3, "o": 2, "w": 1, "r": 1, "d": 1}
```

**Problem 3:** Write a function that takes a list of numbers and returns the average, rounded to 2 decimal places.
```
Input:  [10, 20, 30, 40, 50]
Output: 30.0

Input:  [7, 13, 21]
Output: 13.67
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Arjun  | IT         | 55000  |
| 2      | Asha   | HR         | 42000  |
| 3      | Ravi   | Sales      | 38000  |
| 4      | Priya  | IT         | 60000  |
| 5      | Amit   | HR         | 45000  |

**Table: products**
| product_id | name     | price | category    | stock |
|------------|----------|-------|-------------|-------|
| 1          | Laptop   | 50000 | Electronics | 10    |
| 2          | Mouse    | 500   | Electronics | 50    |
| 3          | Notebook | 100   | Stationery  | 200   |
| 4          | Pen      | 20    | Stationery  | 500   |

**Problem 1:** Write a SQL query to find all employees whose name starts with the letter 'A'.

**Problem 2:** Write a SQL query to count the total number of products in the `products` table.

**Problem 3:** Write a SQL query to find the average price of all products grouped by `category`.

### Part D — OOP Based Problem

Create a class `Pet` with:
- Attributes: `name`, `species` (dog/cat/bird), `age`, `is_vaccinated` (default False)
- Method `vaccinate()` that sets `is_vaccinated` to True
- Method `info()` that returns a formatted string with all details
- Create 3 pets, vaccinate one, and display info for all

### Part E — Django Based Problem

Create a Django model `Product` with fields: `name` (CharField), `description` (TextField), `price` (DecimalField), `stock` (IntegerField), `created_at` (DateTimeField). Register it in admin and write a simple view that returns all products as JSON.
