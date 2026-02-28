# 📝 Question Paper 10 — Medium 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is duck typing in Python? How does it relate to polymorphism?
2. Explain how Django handles file uploads. What storage backends are available?
3. What is `GROUP BY` in SQL? Give a simple example.
4. What is the difference between `is` and `==` in Python?
5. How does DRF handle authentication? Name 2 common authentication methods.
6. What is the `@property` decorator in Python? Give a simple example.
7. What is the difference between `VARCHAR` and `TEXT` in SQL?
8. What is Django's `STATIC_URL`? How do you serve static files in Django?
9. What is an SQL `VIEW`? When would you use one?
10. What is the difference between a REST API and a web application?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python module provides support for asynchronous programming?
2. What SQL constraint prevents NULL values from being inserted?
3. What DRF setting controls the default renderer classes?
4. What Python method creates a shallow copy of a dictionary?
5. What Django app handles user sessions?
6. What HTTP method is idempotent and used to replace a resource entirely?
7. What SQL command is used to grant permissions to a user?
8. What Python testing framework is commonly used with Django?
9. What DRF filter backend allows complex lookups like `gt`, `lt`, `exact`?
10. What Django utility function is used to reverse URL patterns?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of employee dictionaries and returns a summary: total employees, average salary, highest paid employee name, and department-wise count.
```
Input:  [
    {"name": "Ravi", "salary": 50000, "dept": "IT"},
    {"name": "Priya", "salary": 60000, "dept": "IT"},
    {"name": "Karan", "salary": 45000, "dept": "HR"}
]
Output: {"total": 3, "avg_salary": 51666.67, "highest_paid": "Priya", "dept_count": {"IT": 2, "HR": 1}}
```

**Problem 2:** Write a function that deep merges two nested dictionaries. If both have the same key with dict values, merge recursively. Otherwise the second dict's value wins.
```
Input:  {"a": 1, "b": {"c": 2, "d": 3}}, {"b": {"c": 10, "e": 5}, "f": 6}
Output: {"a": 1, "b": {"c": 10, "d": 3, "e": 5}, "f": 6}
```

**Problem 3:** Write a function that takes a list of log strings and returns a summary: total lines, error count, warning count, and the most frequent error message.
```
Input:  [
    "INFO: Server started",
    "ERROR: Connection timeout",
    "WARNING: Slow query",
    "ERROR: Connection timeout",
    "ERROR: Disk full"
]
Output: {"total": 5, "errors": 3, "warnings": 1, "most_frequent_error": "Connection timeout"}
```

**Problem 4:** Write a function that converts a number to words. Handle numbers from 0 to 9999.
```
Input:  1234
Output: "one thousand two hundred thirty four"

Input:  500
Output: "five hundred"
```

### Part C — SQL Live Problems

**Use this table for the problems:**

**Table: employees**
| emp_id | name    | department | salary |
|--------|---------|------------|--------|
| 1      | Ravi    | IT         | 60000  |
| 2      | Priya   | IT         | 55000  |
| 3      | Karan   | HR         | 45000  |
| 4      | Meena   | IT         | 70000  |
| 5      | Arjun   | HR         | 50000  |
| 6      | Divya   | Sales      | 42000  |
| 7      | Suresh  | Sales      | 48000  |

**Problem 1:** Write a SQL query to find the highest salary in each department.

**Problem 2:** Write a SQL query to find employees whose salary is above the average salary of the entire company.

**Problem 3:** Write a SQL query to find departments that have more than 2 employees.

### Part D — OOP Based Problem

Design a notification system:
- `Notification` (abstract base class) with `recipient`, `message`, `timestamp`
  - Abstract method: `send()`
- `EmailNotification`: requires `email_address`, implements `send()`
- `SMSNotification`: requires `phone_number`, implements `send()`
- `PushNotification`: requires `device_token`, implements `send()`
- `NotificationService` class that:
  - Maintains a queue of notifications
  - Can `add_notification()`, `send_all()`, `get_failed_notifications()`
  - Uses the strategy pattern to handle different notification types uniformly

### Part E — Django Based Problem

Build a complete User Authentication API with DRF:
- Endpoints: `POST /register/`, `POST /login/`, `POST /logout/`, `GET /profile/`
- Use Token authentication
- Custom user serializer with password hashing (use `make_password`)
- Profile endpoint should return the logged-in user's details and be accessible only to authenticated users
- Add validation: email must be unique, password must be at least 8 characters

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x for x in [1, [2, 3], 4, [5]] if isinstance(x, list)]
print(result)
```
a) `[1, 4]`
b) `[[2, 3], [5]]`
c) `[2, 3, 5]`
d) `[1, [2, 3], 4, [5]]`

**Q2 (MCQ):** What is the output?
```python
text = "Hello World Python"
result = [word[0].lower() + word[1:] for word in text.split()]
print(result)
```
a) `["Hello", "World", "Python"]`
b) `["hello", "world", "python"]`
c) `["hELLO", "wORLD", "pYTHON"]`
d) `["helloWorldPython"]`

**Q3 (MCQ):** What is the output?
```python
a = [1, 2, 3]
b = [2, 3, 4]
result = [x for x in a if x in b]
print(result)
```
a) `[1, 2, 3, 4]`
b) `[2, 3]`
c) `[1, 4]`
d) `[1]`

**Q4 (Open-Ended):** What is the output?
```python
result = {v: k for k, v in {"a": 1, "b": 2, "c": 3}.items()}
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
nums = [10, 20, 30, 40, 50]
result = [nums[i] - nums[i-1] for i in range(1, len(nums))]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
compose = lambda f, g: lambda x: f(g(x))
double = lambda x: x * 2
add_one = lambda x: x + 1
h = compose(double, add_one)
print(h(3))
```
a) `7`
b) `8`
c) `9`
d) `6`

**Q7 (MCQ):** What is the output?
```python
data = [{"name": "A", "age": 30}, {"name": "B", "age": 25}, {"name": "C", "age": 35}]
result = list(filter(lambda x: x["age"] < 30, data))
print(len(result))
```
a) `0`
b) `1`
c) `2`
d) `3`

**Q8 (MCQ):** What is the output?
```python
nums = [3, 7, 2, 8, 1]
result = min(nums, key=lambda x: abs(x - 5))
print(result)
```
a) `1`
b) `3`
c) `7`
d) `5`

**Q9 (Open-Ended):** What is the output?
```python
from functools import reduce
words = ["Hello", " ", "World", "!"]
result = reduce(lambda a, b: a + b, words)
print(result)
```

**Q10 (Open-Ended):** What is the output?
```python
matrix = [[1, 2], [3, 4], [5, 6]]
flat = list(map(lambda row: row[0] * row[1], matrix))
print(flat)
```
