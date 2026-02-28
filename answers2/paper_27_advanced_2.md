# 📝 Question Paper 27 — Advanced 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between instance methods, class methods, and static methods in Python?
2. What is Django's `get_queryset()` method? How do you override it in a ViewSet?
3. What is the difference between `DELETE`, `TRUNCATE`, and `DROP` in SQL?
4. What are Python generators? How do `yield` and `send()` work?
5. How does DRF handle serializer validation? Explain field-level and object-level validation.
6. What is the `__str__` method in Python? Why is it useful?
7. What is database normalization? Explain with 1NF, 2NF, 3NF examples.
8. What are Django's `F()` expressions? Give 2 practical use cases.
9. What is the difference between a list and a tuple in Python? When would you use each?
10. What are Django custom management commands? How do you create one?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python built-in function creates a dictionary from key-value pairs?
2. What SQL keyword renames a table?
3. What DRF class serializes multiple objects?
4. What Python function merges two dictionaries (3.9+)?
5. What HTTP status code means "Unauthorized"?
6. What built-in function returns the minimum value from a list?
7. What SQL keyword adds a new column to an existing table?
8. What Django method annotates each object in a queryset with computed values?
9. What Python keyword handles exceptions?
10. What does `SSH` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of log entries (timestamp, level, message) and generates a report: total logs per level, most active hour, error messages list, and warning count.
```
Input:  [
    {"time": "2025-01-01 09:15:00", "level": "INFO", "msg": "Server started"},
    {"time": "2025-01-01 09:30:00", "level": "ERROR", "msg": "DB connection failed"},
    {"time": "2025-01-01 09:45:00", "level": "WARNING", "msg": "Slow query"},
    {"time": "2025-01-01 10:00:00", "level": "ERROR", "msg": "Timeout"},
    {"time": "2025-01-01 09:50:00", "level": "INFO", "msg": "Retry success"}
]
Output: {
    "counts": {"INFO": 2, "ERROR": 2, "WARNING": 1},
    "most_active_hour": 9,
    "errors": ["DB connection failed", "Timeout"],
    "warning_count": 1
}
```

**Problem 2:** Write a function that converts a flat dictionary with dot-notation keys into a nested dictionary.
```
Input:  {"a.b.c": 1, "a.b.d": 2, "a.e": 3, "f": 4}
Output: {"a": {"b": {"c": 1, "d": 2}, "e": 3}, "f": 4}
```

**Problem 3:** Write a function that takes a list of scored exam results and applies a bell curve: find the average, and add/subtract the difference so the average becomes 60. Cap at 100.
```
Input:  [45, 50, 55, 40, 60], target_avg = 60
Output: [55, 60, 65, 50, 70]  (added 10 to each)
```

**Problem 4:** Write a function that takes a directory-like structure (list of "path/to/file" strings) and calculates the total number of unique folders and files.
```
Input:  ["src/app/main.py", "src/app/utils.py", "src/tests/test.py", "README.md"]
Output: {"folders": 3, "files": 4}  (src, src/app, src/tests are folders)
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: customers**
| customer_id | name   |
|-------------|--------|
| 1           | Ravi   |
| 2           | Priya  |
| 3           | Karan  |

**Table: products**
| product_id | name     |
|------------|----------|
| 1          | Laptop   |
| 2          | Mouse    |
| 3          | Keyboard |

**Table: orders**
| order_id | customer_id | product_id | amount | order_date |
|----------|-------------|------------|--------|------------|
| 1        | 1           | 1          | 50000  | 2024-01-10 |
| 2        | 1           | 2          | 500    | 2024-01-15 |
| 3        | 1           | 3          | 1500   | 2024-02-01 |
| 4        | 2           | 1          | 50000  | 2024-02-10 |
| 5        | 2           | 2          | 500    | 2024-02-15 |
| 6        | 2           | 3          | 1500   | 2024-03-01 |
| 7        | 3           | 1          | 50000  | 2024-03-10 |

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 70000  |
| 2      | Priya  | IT         | 55000  |
| 3      | Karan  | HR         | 48000  |
| 4      | Meena  | HR         | 60000  |
| 5      | Arjun  | Sales      | 52000  |

**Problem 1:** Write a SQL query to find customers who have placed more than 2 orders.

**Problem 2:** Write a SQL query to find the total order amount per customer, showing their name and total.

**Problem 3:** Write a SQL query to find the highest salary in each department.

### Part D — OOP Based Problem

Design a simple employee payroll system:
- `Employee` base class with `name`, `emp_id`, `base_salary`
- `FullTimeEmployee(Employee)` — gets full salary + 10% bonus
- `PartTimeEmployee(Employee)` — gets hourly rate × hours worked
- `ContractEmployee(Employee)` — gets fixed contract amount
- `Payroll` class with:
  - `add_employee(emp)`, `remove_employee(emp_id)`, `calculate_payroll()`
  - `calculate_payroll()` returns dict of emp_id: pay_amount for all employees
  - `total_payout()` returns total salary expense
  - `payroll_report()` returns formatted report
- Demonstrate with 2 of each type

### Part E — Django Based Problem

Build a DRF API for a Blog with comments:
- Models: `Post` (title, body, author_name, category, is_published, created_at, updated_at) and `Comment` (post FK, commenter_name, text, created_at)
- Nested serializer: show comments when fetching a single post
- Post ViewSet with full CRUD
- Comment ViewSet scoped under posts: `/api/posts/{post_id}/comments/`
- Custom action on Post: `POST /posts/{id}/publish/` to toggle publish status
- Only published posts shown in listing; admin can see all via query param `?show_all=true`

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [hex(x) for x in [10, 16, 255]]
print(result)
```
a) `[10, 16, 255]`
b) `["0xa", "0x10", "0xff"]`
c) `["a", "10", "ff"]`
d) `["10", "16", "255"]`

**Q2 (MCQ):** What is the output?
```python
import string
result = [c for c in "Hello123!" if c in string.ascii_letters]
print(len(result))
```
a) `9`
b) `8`
c) `5`
d) `3`

**Q3 (MCQ):** What is the output?
```python
data = {"x": 10, "y": 20, "z": 30}
result = {v: k for k, v in data.items() if v >= 20}
print(result)
```
a) `{10: "x", 20: "y", 30: "z"}`
b) `{20: "y", 30: "z"}`
c) `{"y": 20, "z": 30}`
d) `{10: "x"}`

**Q4 (Open-Ended):** What is the output?
```python
nums = [[1, 2, 3], [4, 5], [6]]
lengths = [len(sub) for sub in nums]
print(lengths)
```

**Q5 (Open-Ended):** What is the output?
```python
result = [i * j for i in range(1, 4) for j in range(1, 4) if i == j]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
clamp = lambda x, low, high: max(low, min(x, high))
print(clamp(15, 0, 10))
print(clamp(-5, 0, 10))
```
a) `15` then `-5`
b) `10` then `0`
c) `0` then `10`
d) `10` then `-5`

**Q7 (MCQ):** What is the output?
```python
data = ["banana", "apple", "cherry"]
result = sorted(data, key=lambda s: (len(s), s))
print(result)
```
a) `["apple", "banana", "cherry"]`
b) `["apple", "banana", "cherry"]`
c) `["apple", "cherry", "banana"]`
d) `["cherry", "banana", "apple"]`

**Q8 (MCQ):** What is the output?
```python
to_dict = lambda keys, values: dict(zip(keys, values))
print(to_dict(["a", "b", "c"], [1, 2, 3]))
```
a) `[("a", 1), ("b", 2), ("c", 3)]`
b) `{"a": 1, "b": 2, "c": 3}`
c) `{"a": "1", "b": "2", "c": "3"}`
d) `Error`

**Q9 (Open-Ended):** What is the output?
```python
pipeline = lambda x, *fns: [f(x) for f in fns]
print(pipeline(10, lambda x: x+1, lambda x: x*2, lambda x: x//3))
```

**Q10 (Open-Ended):** What is the output?
```python
group_by = lambda lst, fn: {}
data = [1, 2, 3, 4, 5, 6]
groups = {}
for x in data:
    key = (lambda n: "even" if n % 2 == 0 else "odd")(x)
    groups.setdefault(key, []).append(x)
print(groups)
```
