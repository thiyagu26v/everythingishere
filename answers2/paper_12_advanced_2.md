# 📝 Question Paper 12 — Advanced 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `__str__` and `__repr__`? When does Python call each one?
2. How does Django's `transaction.atomic()` work? Why is it useful?
3. What are SQL views? How are they different from tables?
4. What is the `__init__` method in Python? How is it different from regular methods?
5. How does DRF authentication work? What is Token authentication?
6. What are list comprehensions vs generator expressions in Python? What's the memory difference?
7. What is query optimization in SQL? How do you find slow queries?
8. How does Django's class-based view work? Explain `get()` and `post()` methods.
9. What is the difference between SQL and NoSQL databases? Give examples of each.
10. What is polymorphism in Python? Give a simple example.

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python data structure allows you to add/remove from both ends?
2. What SQL isolation level provides the highest level of isolation?
3. What DRF component handles converting between Python objects and rendered content?
4. What Python keyword is used before a yield statement in a generator?
5. What Django field type is used for storing JSON data?
6. What HTTP caching header indicates how long a response can be cached?
7. What SQL concept ensures that committed transactions are permanent?
8. What Python module provides high-level thread-based parallelism?
9. What DRF mechanism allows you to include/exclude fields dynamically?
10. What Django class is used for running management commands?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a nested list of product categories and flattens it into a list of paths. Each path shows the full hierarchy.
```
Input:  {
    "Electronics": {
        "Phones": ["iPhone", "Samsung"],
        "Laptops": ["Dell", "HP"]
    },
    "Clothing": ["Shirts", "Pants"]
}
Output: [
    "Electronics > Phones > iPhone",
    "Electronics > Phones > Samsung",
    "Electronics > Laptops > Dell",
    "Electronics > Laptops > HP",
    "Clothing > Shirts",
    "Clothing > Pants"
]
```

**Problem 2:** Write a function that takes a list of time ranges (start, end) and merges overlapping ranges.
```
Input:  [(1, 3), (2, 6), (8, 10), (15, 18), (9, 11)]
Output: [(1, 6), (8, 11), (15, 18)]
```

**Problem 3:** Write a class `Table` that stores rows as list of dictionaries and supports: `filter(**kwargs)`, `order_by(column)`, `select(*columns)`, `group_by(column, agg_column, agg_func)`. Use method chaining.
```
t = Table([
    {"name": "Ravi", "dept": "IT", "salary": 50000},
    {"name": "Priya", "dept": "IT", "salary": 60000},
    {"name": "Karan", "dept": "HR", "salary": 45000}
])
t.filter(dept="IT").select("name", "salary").order_by("salary")
Output: [{"name": "Ravi", "salary": 50000}, {"name": "Priya", "salary": 60000}]
```

**Problem 4:** Write a function that takes a list of tasks with dependencies and returns them sorted so that dependent tasks come after the tasks they depend on. Each task depends on at most one other task.
```
Input:  [{"task": "deploy", "depends_on": "build"}, {"task": "build", "depends_on": "test"}, {"task": "test", "depends_on": None}]
Output: ["test", "build", "deploy"]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary | hire_date  |
|--------|--------|------------|--------|------------|
| 1      | Ravi   | IT         | 60000  | 2023-01-10 |
| 2      | Priya  | IT         | 60000  | 2023-05-15 |
| 3      | Karan  | HR         | 50000  | 2024-01-20 |
| 4      | Meena  | Sales      | 55000  | 2023-08-12 |
| 5      | Arjun  | IT         | 65000  | 2024-03-01 |

**Table: sales**
| sale_id | employee_id | amount | sale_month |
|---------|-------------|--------|------------|
| 1       | 1           | 15000  | Jan        |
| 2       | 1           | 20000  | Feb        |
| 3       | 1           | 18000  | Mar        |
| 4       | 2           | 12000  | Jan        |
| 5       | 2           | 16000  | Feb        |

**Problem 1:** Write a SQL query to find employees who have the same salary (showing both names and the salary).

**Problem 2:** Write a SQL query to find each employee's total sales across all months.

**Problem 3:** Write a SQL query to find employees whose salary is above the average salary in their department.

### Part D — OOP Based Problem

Design a file processing system using the Strategy pattern:
- `FileProcessor` class that reads a file and processes it based on a strategy
- Strategy interface: `ProcessingStrategy` with method `process(data) -> result`
- Concrete strategies:
  - `CSVProcessor` — parses CSV and returns list of dicts
  - `JSONProcessor` — parses JSON and returns Python object
  - `XMLProcessor` — parses XML and returns nested dict
- `ProcessorFactory` that returns the correct strategy based on file extension
- `FileReport` class that generates a summary report (row count, column names, data types) from processed data
- Demonstrate with at least 2 file types

### Part E — Django Based Problem

Build a URL Shortener API with DRF:
- Model: `ShortURL` (original_url, short_code unique, created_by FK User, click_count, created_at, expires_at nullable)
- Auto-generate a unique 6-character `short_code` on creation
- `GET /s/{short_code}/` — redirects to original URL and increments click_count
- `GET /api/urls/` — list all URLs created by the authenticated user
- `POST /api/urls/` — create a new short URL
- `GET /api/urls/{id}/stats/` — return click_count, created_at, last accessed info
- Expired URLs should return 410 Gone
- Rate limiting: max 10 URL creations per hour per user

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [f"{k}={v}" for k, v in {"x": 1, "y": 2, "z": 3}.items()]
print(result)
```
a) `["x1", "y2", "z3"]`
b) `["x=1", "y=2", "z=3"]`
c) `{"x": 1, "y": 2, "z": 3}`
d) `[("x", 1), ("y", 2), ("z", 3)]`

**Q2 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = [nums[:i+1] for i in range(len(nums))]
print(result)
```
a) `[[1], [2], [3], [4], [5]]`
b) `[[1], [1, 2], [1, 2, 3], [1, 2, 3, 4], [1, 2, 3, 4, 5]]`
c) `[1, 3, 6, 10, 15]`
d) `[[5], [4, 5], [3, 4, 5], [2, 3, 4, 5], [1, 2, 3, 4, 5]]`

**Q3 (MCQ):** What is the output?
```python
text = "hello"
result = [text[:i] + text[i].upper() + text[i+1:] for i in range(len(text))]
print(result[2])
```
a) `"Hello"`
b) `"hEllo"`
c) `"heLlo"`
d) `"helLo"`

**Q4 (Open-Ended):** What is the output?
```python
result = [x for x in range(100) if x == x[::-1] if isinstance(x, str)]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
nums = [1, 2, 3, 4]
result = [(a, b) for a in nums for b in nums if a < b]
print(len(result))
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
make_adder = lambda n: lambda x: x + n
add_5 = make_adder(5)
add_10 = make_adder(10)
print(add_5(3), add_10(3))
```
a) `5 10`
b) `8 13`
c) `3 3`
d) `15 30`

**Q7 (MCQ):** What is the output?
```python
data = ["hello world", "foo bar", "python"]
result = list(map(lambda s: s.split()[0] if " " in s else s, data))
print(result)
```
a) `["hello world", "foo bar", "python"]`
b) `["hello", "foo", "python"]`
c) `["world", "bar", "python"]`
d) `["h", "f", "p"]`

**Q8 (MCQ):** What is the output?
```python
records = [("A", 90), ("B", 80), ("C", 95), ("D", 85)]
passed = list(filter(lambda r: r[1] >= 85, records))
print([x[0] for x in passed])
```
a) `["A", "C", "D"]`
b) `["A", "C"]`
c) `["B", "D"]`
d) `[90, 95, 85]`

**Q9 (Open-Ended):** What is the output?
```python
nums = [4, 2, 7, 1, 8]
result = sorted(enumerate(nums), key=lambda x: x[1])
print(result[0])
```

**Q10 (Open-Ended):** What is the output?
```python
funcs = {"double": lambda x: x * 2, "square": lambda x: x ** 2, "negate": lambda x: -x}
print(funcs["square"](funcs["double"](3)))
```
