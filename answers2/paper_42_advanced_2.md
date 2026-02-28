# 📝 Question Paper 42 — Advanced 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the `__init__` method in Python? Why is it important for classes?
2. What are Django management commands? How would you create a custom one?
3. What is a Common Table Expression (CTE) in SQL? How is it used?
4. What is inheritance in Python? Give a simple example with parent and child class.
5. What is the difference between `HyperlinkedModelSerializer` and `ModelSerializer` in DRF?
6. What is the `string` module in Python? Name 3 useful string methods.
7. What is the difference between a unique constraint and a unique index?
8. What is Django's `STATIC_ROOT`? What is the difference between `collectstatic` and serving static files in development?
9. What is a Python `defaultdict`? Give an example where it simplifies code.
10. What is webhook? How is it different from polling an API?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function converts bytes to a string?
2. What SQL keyword rolls back a transaction?
3. What DRF mixin provides the update functionality?
4. What Python method capitalizes only the first letter of a string?
5. What HTTP status code means "Not Acceptable"?
6. What built-in function returns an object's string representation?
7. What SQL keyword combines results from two SELECT queries?
8. What Django ORM method checks if any records exist?
9. What Python module provides tools for working with dates?
10. What does `CI/CD` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of student records (name, subjects with marks) and generates a class report: class average, topper, weakest student, subject-wise averages, and pass/fail count (passing = 40%).
```
Input:  [
    {"name": "Ravi", "marks": {"Math": 85, "Science": 90, "English": 78}},
    {"name": "Priya", "marks": {"Math": 35, "Science": 42, "English": 55}},
    {"name": "Karan", "marks": {"Math": 70, "Science": 65, "English": 80}}
]
Output: {
    "class_avg": 66.67,
    "topper": "Ravi",
    "weakest": "Priya",
    "subject_avg": {"Math": 63.33, "Science": 65.67, "English": 71.0},
    "passed": 2,
    "failed": 1
}
```

**Problem 2:** Write a function that takes a date string and a number of working days, and returns the future date after adding those working days (skip Saturday and Sunday).
```
Input:  "2025-01-06", 5  (Monday)
Output: "2025-01-13"     (next Monday, skipping Sat-Sun)

Input:  "2025-01-06", 10
Output: "2025-01-20"
```

**Problem 3:** Write a function that takes a dict of product prices in INR and converts them to multiple currencies using given exchange rates.
```
Input:  prices = {"Laptop": 50000, "Mouse": 500}
        rates = {"USD": 0.012, "EUR": 0.011, "GBP": 0.0095}
Output: {
    "Laptop": {"USD": 600.0, "EUR": 550.0, "GBP": 475.0},
    "Mouse": {"USD": 6.0, "EUR": 5.5, "GBP": 4.75}
}
```

**Problem 4:** Write a function that takes a flat list of `{"id", "name", "manager_id"}` records and builds an organizational hierarchy as a nested dict.
```
Input:  [
    {"id": 1, "name": "CEO", "manager_id": None},
    {"id": 2, "name": "VP Eng", "manager_id": 1},
    {"id": 3, "name": "Dev", "manager_id": 2},
    {"id": 4, "name": "VP Sales", "manager_id": 1}
]
Output: {"CEO": {"VP Eng": {"Dev": {}}, "VP Sales": {}}}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: customers**
| customer_id | name   | city    |
|-------------|--------|---------|
| 1           | Ravi   | Chennai |
| 2           | Priya  | Mumbai  |
| 3           | Karan  | Chennai |
| 4           | Meena  | Delhi   |

**Table: orders**
| order_id | customer_id | product_id | amount | order_date |
|----------|-------------|------------|--------|------------|
| 1        | 1           | 1          | 50000  | 2024-01-10 |
| 2        | 1           | 2          | 500    | 2024-01-15 |
| 3        | 2           | 1          | 50000  | 2024-02-01 |
| 4        | 3           | 2          | 500    | 2024-02-10 |
| 5        | 1           | 3          | 1500   | 2024-03-01 |

**Table: products**
| product_id | name     |
|------------|----------|
| 1          | Laptop   |
| 2          | Mouse    |
| 3          | Keyboard |

**Problem 1:** Write a SQL query to find customers who have placed orders for more than one different product.

**Problem 2:** Write a SQL query to find the total number of orders and total amount spent by each customer.

**Problem 3:** Write a SQL query to find each customer's most recent order date and amount.

### Part D — OOP Based Problem

Design an e-learning quiz platform:
- `Question` class with `question_id`, `text`, `options` (list), `correct_option` (index), `difficulty` (easy/medium/hard), `points`
- `QuizSession` class with:
  - `start(questions_list)` — begins quiz with a set of questions
  - `answer(question_id, answer_index)` — records answer
  - `skip(question_id)` — marks as skipped
  - `finish()` — ends quiz, calculates results
  - `result()` — returns: total score, max possible, percentage, correct/wrong/skipped counts, time taken
  - `review()` — shows each question with user's answer, correct answer, and status
- `QuestionBank` with `add_question()`, `get_random_quiz(n, difficulty)` — picks n random questions of given difficulty
- Demonstrate: create 15 questions, generate a quiz of 5, answer all, show results

### Part E — Django Based Problem

Build a DRF API for a Polling System:
- Models: `Poll` (question, description, is_active, created_at, expires_at) and `Choice` (poll FK, text, votes IntegerField default 0)
- Poll serializer shows choices nested with vote counts
- ViewSets for both
- Custom action: `POST /polls/{id}/vote/` — accepts `choice_id`, increments vote count
- Custom action: `GET /polls/{id}/results/` — returns each choice with vote count and percentage
- Only active, non-expired polls shown in listing
- Prevent voting on expired polls

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
data = [{"x": 1, "y": 2}, {"x": 3, "y": 4}]
result = [d["x"] + d["y"] for d in data]
print(result)
```
a) `[{"x": 1, "y": 2}, {"x": 3, "y": 4}]`
b) `[3, 7]`
c) `[1, 3]`
d) `[2, 4]`

**Q2 (MCQ):** What is the output?
```python
import re
emails = ["a@b.com", "invalid", "c@d.org", "nope"]
result = [e for e in emails if "@" in e and "." in e]
print(result)
```
a) `["a@b.com", "invalid", "c@d.org", "nope"]`
b) `["a@b.com", "c@d.org"]`
c) `["invalid", "nope"]`
d) `[True, False, True, False]`

**Q3 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
result = [x for x in nums if x % 2 == 0 if x % 3 == 0]
print(result)
```
a) `[2, 4, 6, 8, 10]`
b) `[3, 6, 9]`
c) `[6]`
d) `[6, 12]`

**Q4 (Open-Ended):** What is the output?
```python
s = "abcde"
result = [(s[i], s[j]) for i in range(len(s)) for j in range(i+1, len(s))]
print(len(result))
```

**Q5 (Open-Ended):** What is the output?
```python
data = {"python": 3, "java": 5, "go": 2}
sorted_keys = [k for k, v in sorted(data.items(), key=lambda x: x[1])]
print(sorted_keys)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
validators = {
    "positive": lambda x: x > 0,
    "even": lambda x: x % 2 == 0,
    "small": lambda x: x < 100
}
num = 50
result = {k: v(num) for k, v in validators.items()}
print(result)
```
a) `{"positive": True, "even": True, "small": True}`
b) `{"positive": 50, "even": 50, "small": 50}`
c) `True`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
adders = [lambda x, i=i: x + i for i in range(4)]
result = [f(10) for f in adders]
print(result)
```
a) `[10, 10, 10, 10]`
b) `[10, 11, 12, 13]`
c) `[13, 13, 13, 13]`
d) `[14, 14, 14, 14]`

**Q8 (MCQ):** What is the output?
```python
process = lambda s: s.strip().lower().replace(" ", "_")
print(process("  Hello World  "))
```
a) `"Hello World"`
b) `"hello_world"`
c) `"  hello_world  "`
d) `"hello world"`

**Q9 (Open-Ended):** What is the output?
```python
either = lambda pred, a, b: a if pred else b
results = [either(x > 0, "pos", "non-pos") for x in [3, -1, 0, 5]]
print(results)
```

**Q10 (Open-Ended):** What is the output?
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
transpose = list(map(lambda *row: list(row), *matrix))
print(transpose[1])
```
