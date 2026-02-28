# 📝 Question Paper 22 — Medium 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `append()` and `extend()` in Python lists?
2. What is the `get_object_or_404` function in Django? When do you use it?
3. What is the difference between `LEFT JOIN` and `CROSS JOIN` in SQL?
4. What are Python comprehensions? Explain list, dict, and set comprehension.
5. What is pagination in DRF? Name the different pagination types.
6. What is the purpose of `__init__.py` in a Python package?
7. What is a SQL transaction? Explain COMMIT and ROLLBACK.
8. What is Django's `related_name` in ForeignKey? Why is it useful?
9. What is the difference between a module and a package in Python?
10. What is abstraction in OOP? How do you achieve it in Python?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method sorts a list in-place?
2. What SQL keyword is used to check for NULL values?
3. What DRF class provides pagination for API responses?
4. What Python function creates a range of numbers?
5. What HTTP status code means "Forbidden"?
6. What built-in function converts an iterable of tuples into a dictionary?
7. What SQL function returns the length of a string?
8. What Django model field stores a reference to another model?
9. What Python keyword is used to raise an exception manually?
10. What does `REST` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of numbers and replaces each number with the product of all other numbers in the list (without using division).
```
Input:  [1, 2, 3, 4]
Output: [24, 12, 8, 6]
```

**Problem 2:** Write a function that groups a list of dictionaries by a given key.
```
Input:  data = [
    {"name": "Ravi", "dept": "IT"},
    {"name": "Priya", "dept": "HR"},
    {"name": "Karan", "dept": "IT"},
    {"name": "Meena", "dept": "HR"}
]
group_by(data, "dept")

Output: {"IT": [{"name": "Ravi", "dept": "IT"}, {"name": "Karan", "dept": "IT"}],
         "HR": [{"name": "Priya", "dept": "HR"}, {"name": "Meena", "dept": "HR"}]}
```

**Problem 3:** Write a function that takes a list of tuples (name, score) and returns the top 3 scorers.
```
Input:  [("Ravi", 85), ("Priya", 92), ("Karan", 78), ("Meena", 95), ("Arjun", 88)]
Output: [("Meena", 95), ("Priya", 92), ("Arjun", 88)]
```

**Problem 4:** Write a function that takes a dictionary and returns a new dictionary with keys and values swapped. If multiple keys have the same value, store them as a list.
```
Input:  {"a": 1, "b": 2, "c": 1}
Output: {1: ["a", "c"], 2: "b"}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: customers**
| customer_id | name   |
|-------------|--------|
| 1           | Ravi   |
| 2           | Priya  |
| 3           | Karan  |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 1           | 5000   | 2024-01-10 |
| 2        | 1           | 3000   | 2024-02-15 |
| 3        | 1           | 7000   | 2024-03-01 |
| 4        | 1           | 2000   | 2024-03-20 |
| 5        | 2           | 4500   | 2024-02-28 |

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 25000  |
| 2      | Priya  | IT         | 55000  |
| 3      | Karan  | HR         | 45000  |
| 4      | Meena  | Sales      | 75000  |
| 5      | Arjun  | HR         | 45000  |

**Problem 1:** Write a SQL query to find customers who have placed more than 3 orders.

**Problem 2:** Write a SQL query using `CASE WHEN` to add a column `salary_level` that says 'Junior' for salary < 30000, 'Mid' for 30000-60000, 'Senior' for > 60000.

**Problem 3:** Write a SQL query to find employees whose salary is equal to the average salary of their department.

### Part D — OOP Based Problem

Create a simple grading system:
- `Student` class with `name`, `marks` (dict of subject: marks)
- Methods: `add_marks(subject, marks)`, `total()`, `percentage()`, `grade()`, `report_card()`
- Grading: A (>= 90), B (>= 75), C (>= 60), D (>= 40), F (< 40)
- `report_card()` returns a formatted string with all subjects, total, percentage, and grade
- Create 3 students with different marks and display their report cards

### Part E — Django Based Problem

Build a DRF API for a Library system:
- Models: `Author` (name, bio, birth_date) and `Book` (title, author FK, isbn, published_year, genre, available_copies)
- Nested serializer: when fetching a book, include author's name and bio
- Create viewsets for both models
- Add filter: books by genre, published_year range
- Add search on book title and author name
