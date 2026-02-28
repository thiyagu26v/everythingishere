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

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [len(w) for w in "I love Python".split()]
print(result)
```
a) `["I", "love", "Python"]`
b) `[1, 4, 6]`
c) `[3]`
d) `11`

**Q2 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5, 6]
evens = [x for x in nums if x % 2 == 0]
odds = [x for x in nums if x % 2 != 0]
print(evens, odds)
```
a) `[1, 3, 5] [2, 4, 6]`
b) `[2, 4, 6] [1, 3, 5]`
c) `[1, 2, 3, 4, 5, 6] []`
d) `[] [1, 2, 3, 4, 5, 6]`

**Q3 (MCQ):** What is the output?
```python
matrix = [[1, 2], [3, 4]]
result = [col for row in matrix for col in row]
print(result)
```
a) `[[1, 2], [3, 4]]`
b) `[1, 2, 3, 4]`
c) `[(1, 3), (2, 4)]`
d) `[1, 3, 2, 4]`

**Q4 (Open-Ended):** What is the output?
```python
d = {"name": "Ravi", "age": 25, "city": "Chennai"}
result = [f"{k}: {v}" for k, v in d.items()]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
words = ["hello", "world"]
result = [c.upper() for word in words for c in word if c in "aeiou"]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
safe_divide = lambda a, b: a / b if b != 0 else "Cannot divide by zero"
print(safe_divide(10, 0))
```
a) `Error`
b) `0`
c) `"Cannot divide by zero"`
d) `None`

**Q7 (MCQ):** What is the output?
```python
data = [(3, "c"), (1, "a"), (2, "b")]
result = sorted(data, key=lambda x: x[0])
print([x[1] for x in result])
```
a) `["c", "a", "b"]`
b) `["a", "b", "c"]`
c) `[1, 2, 3]`
d) `["a", "c", "b"]`

**Q8 (MCQ):** What is the output?
```python
funcs = [lambda x: x + 1, lambda x: x * 2, lambda x: x - 3]
results = [f(10) for f in funcs]
print(results)
```
a) `[11, 20, 7]`
b) `[10, 10, 10]`
c) `[11, 12, 9]`
d) `30`

**Q9 (Open-Ended):** What is the output?
```python
power = lambda base, exp=2: base ** exp
print(power(3))
print(power(2, 5))
```

**Q10 (Open-Ended):** What is the output?
```python
students = [("A", [80, 90, 70]), ("B", [60, 70, 80]), ("C", [90, 95, 85])]
result = sorted(students, key=lambda s: sum(s[1]) / len(s[1]), reverse=True)
print(result[0][0])
```
