# 📝 Question Paper 16 — Easy 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is an interpreted language? Why is Python called interpreted?
2. What is the difference between a set and a list in Python?
3. What does `urls.py` do in a Django project? How does URL routing work?
4. What is the difference between `CHAR` and `VARCHAR` in SQL?
5. What is JSON? Why is it used in APIs?
6. What is the difference between `print()` and `return` in a function?
7. What does `migrate` command do in Django?
8. What is the difference between `WHERE` and `HAVING` in SQL?
9. What is version control? Why do developers use Git?
10. What is the difference between a class and an object in Python?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What built-in function converts an integer to a string in Python?
2. What SQL keyword removes all rows from a table without deleting the table?
3. What is the file name where Django project settings are stored?
4. What Python keyword stops a loop immediately?
5. What HTTP status code means "OK" (success)?
6. What command installs a Python package using pip?
7. What SQL keyword is used to create a new database?
8. What Python method removes whitespace from both ends of a string?
9. What Django command collects static files?
10. What does `API` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of numbers and returns a new list with only the positive numbers.
```
Input:  [-3, 5, -1, 8, 0, -2, 7]
Output: [5, 8, 7]
```

**Problem 2:** Write a function that takes a string and counts how many vowels it contains.
```
Input:  "Hello World"
Output: 3
```

**Problem 3:** Write a function that takes two strings and checks if one is an anagram of the other.
```
Input:  "listen", "silent"
Output: True

Input:  "hello", "world"
Output: False
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: products**
| product_id | name      | price | category    | stock |
|------------|-----------|-------|-------------|-------|
| 1          | Laptop    | 50000 | Electronics | 10    |
| 2          | Mouse     | 350   | Electronics | 50    |
| 3          | Notebook  | 150   | Stationery  | 200   |
| 4          | Pen       | 20    | Stationery  | 500   |
| 5          | Headphone | 2500  | Electronics | 25    |

**Table: customers**
| customer_id | name   | email              |
|-------------|--------|--------------------|
| 1           | Ravi   | ravi@gmail.com     |
| 2           | Priya  | priya@yahoo.com    |
| 3           | Karan  | karan@gmail.com    |

**Table: orders**
| order_id | customer_id | product_id | quantity | order_date |
|----------|-------------|------------|----------|------------|
| 1        | 1           | 1          | 1        | 2024-01-10 |
| 2        | 1           | 2          | 2        | 2024-02-15 |
| 3        | 2           | 3          | 5        | 2024-03-01 |
| 4        | 3           | 1          | 1        | 2024-03-20 |

**Problem 1:** Write a SQL query to select all products from the `products` table where `price` is between 100 and 500.

**Problem 2:** Write a SQL query to find all customers whose `email` ends with `@gmail.com`.

**Problem 3:** Write a SQL query to get the total number of orders placed by each customer from the `orders` table.

### Part D — OOP Based Problem

Create a class `Book` with:
- Attributes: `title`, `author`, `pages`, `is_read` (default False)
- Method `mark_as_read()` that sets `is_read` to True
- Method `summary()` that returns a string like "Title by Author, 200 pages, Read/Unread"
- Create 3 book objects, mark one as read, and print summaries of all

### Part E — Django Based Problem

Create a Django app called `contacts`. Define a model `Contact` with fields: `first_name` (CharField), `last_name` (CharField), `email` (EmailField), `phone` (CharField), `created_at` (DateTimeField). Register the model in admin and create the migration.
