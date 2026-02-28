# 📝 Question Paper 34 — Easy 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is a Python decorator at a high level? What does it do?
2. What is the difference between a Django project and a Django app?
3. What is a primary key in SQL? Why is it important?
4. What is the difference between `None`, `0`, `""`, and `False` in Python?
5. What is a query parameter in a URL? Give an example.
6. What is error handling in Python? What keywords are used?
7. What does `AS` keyword do in SQL?
8. What is CSRF protection in Django? Why is it needed?
9. What is a package manager? Name 2 Python package managers.
10. What is the difference between `remove()` and `pop()` in Python lists?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method converts a list to a comma-separated string?
2. What SQL operator checks if a value falls within a range?
3. What Django model field auto-generates an ID?
4. What Python keyword exits a function and returns a value?
5. What HTTP status code means "No Content"?
6. What function opens a file in Python?
7. What SQL keyword sets conditions on grouped data?
8. What DRF class converts model instances to JSON?
9. What Python method counts occurrences of an element in a list?
10. What does `SQL` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of integers and separates them into two lists: odd numbers and even numbers.
```
Input:  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Output: {"odd": [1, 3, 5, 7, 9], "even": [2, 4, 6, 8, 10]}
```

**Problem 2:** Write a function that takes a sentence and capitalizes the first letter of each word (without using `.title()`).
```
Input:  "hello world from python"
Output: "Hello World From Python"
```

**Problem 3:** Write a function that takes a list of prices and applies a discount percentage, returning the new prices rounded to 2 decimals.
```
Input:  [100, 250.50, 75.99], discount = 10
Output: [90.0, 225.45, 68.39]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: products**
| product_id | name     | price | stock | category    |
|------------|----------|-------|-------|-------------|
| 1          | Laptop   | 50000 | 0     | Electronics |
| 2          | Mouse    | 500   | 50    | Electronics |
| 3          | Notebook | 100   | 0     | Stationery  |
| 4          | Pen      | 20    | 500   | Stationery  |

**Table: categories**
| id | name        |
|----|-------------|
| 1  | Electronics |
| 2  | Stationery  |
| 3  | Furniture   |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 101         | 5000   | 2024-01-10 |
| 2        | 101         | 3000   | 2024-03-15 |
| 3        | 102         | 7000   | 2024-02-20 |
| 4        | 103         | 2000   | 2024-04-05 |

**Problem 1:** Write a SQL query to find all products whose stock is zero.

**Problem 2:** Write a SQL query to insert 3 rows into the `categories` table with columns `id`, `name`.

**Problem 3:** Write a SQL query to find the most recent order date for each customer.

### Part D — OOP Based Problem

Create a class `Student` with:
- Attributes: `name`, `roll_number`, `subjects` (dict of subject: marks)
- Methods: `add_subject(subject, marks)`, `total_marks()`, `average()`, `highest_subject()`
- `highest_subject()` returns the subject name where the student scored the most
- Create 2 students, add 4 subjects each, and display their totals and highest subjects

### Part E — Django Based Problem

Create a DRF API for a `Note` model with fields: `title` (CharField), `body` (TextField), `category` (CharField), `created_at` (DateTimeField, auto). Use `APIView` to create list (GET) and create (POST) endpoints. Return proper status codes.
