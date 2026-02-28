# 📝 Question Paper 04 — Easy 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `args` and `kwargs` in Python?
2. What is a migration in Django? Why is it important?
3. What is the difference between `WHERE` and `HAVING` in SQL?
4. What are Python's built-in data structures? Name all of them.
5. What is the Django admin panel? How do you register a model?
6. What is exception handling in Python? Name the keywords used.
7. What is the difference between `views.py` function-based views and class-based views?
8. What is a queryset in Django?
9. What is the difference between `DELETE` and `TRUNCATE` in SQL?
10. What is `pip freeze` and why is it useful?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python built-in function returns a sorted version of a list?
2. What SQL keyword is used to combine rows from two tables?
3. What is the default database used by Django?
4. What Python method splits a string into a list?
5. What does `JSON` stand for?
6. What command creates a new app inside a Django project?
7. What operator is used for floor division in Python?
8. What SQL function returns the total sum of a numeric column?
9. What HTTP status code means "Not Found"?
10. What Python module is used for working with dates and times?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that accepts a list of words and returns the longest word.
```
Input:  ["cat", "elephant", "dog", "tiger"]
Output: "elephant"
```

**Problem 2:** Write a program that creates a dictionary from two lists — one of keys and one of values.
```
Input:  keys = ["name", "age", "city"], values = ["Ravi", 25, "Chennai"]
Output: {"name": "Ravi", "age": 25, "city": "Chennai"}
```

**Problem 3:** Write a function that takes a sentence and returns the number of words in it.
```
Input:  "Hello world this is Python"
Output: 5
```

### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name    | department | salary |
|--------|---------|------------|--------|
| 1      | Arjun   | IT         | 55000  |
| 2      | Anita   | HR         | 40000  |
| 3      | Ravi    | IT         | 48000  |
| 4      | Priya   | Sales      | 42000  |
| 5      | Arun    | Sales      | 38000  |
| 6      | Karan   | HR         | 45000  |

**Problem 1:** Write a SQL query to find the highest salary in the `employees` table.

**Problem 2:** Write a SQL query to find all employees whose name starts with the letter 'A'.

**Problem 3:** Write a SQL query to count employees in each department using `GROUP BY`.

### Part D — OOP Based Problem

Create a class `Car` with:
- Attributes: `brand`, `model`, `year`, `is_running` (default False)
- Methods: `start()`, `stop()`, `display_status()`
- `start()` sets `is_running` to True, `stop()` sets it to False
- Create a car object, start it, display status, stop it, display status again

### Part E — Django Based Problem

Create a simple DRF serializer for a `Product` model that has fields: `id`, `name`, `price`, `description`. Write the serializer class in `serializers.py`.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [str(x) for x in [1, 2, 3]]
print(result)
```
a) `[1, 2, 3]`
b) `["1", "2", "3"]`
c) `["one", "two", "three"]`
d) `Error`

**Q2 (MCQ):** What is the output?
```python
result = [x for x in range(1, 10) if x % 2 == 0 and x > 4]
print(result)
```
a) `[2, 4, 6, 8]`
b) `[6, 8]`
c) `[5, 6, 7, 8, 9]`
d) `[4, 6, 8]`

**Q3 (MCQ):** What is the output?
```python
result = [fruit[:3] for fruit in ["apple", "banana", "cherry"]]
print(result)
```
a) `["app", "ban", "che"]`
b) `["a", "b", "c"]`
c) `["apple", "banana", "cherry"]`
d) `["le", "na", "ry"]`

**Q4 (Open-Ended):** What is the output?
```python
result = [True if x > 3 else False for x in [1, 2, 3, 4, 5]]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
pairs = [(1, "a"), (2, "b"), (3, "c")]
result = [num for num, letter in pairs]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
is_even = lambda x: x % 2 == 0
print(is_even(7))
```
a) `True`
b) `False`
c) `1`
d) `0`

**Q7 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4]
result = list(map(lambda x: str(x), nums))
print(result)
```
a) `[1, 2, 3, 4]`
b) `["1", "2", "3", "4"]`
c) `["one", "two", "three", "four"]`
d) `Error`

**Q8 (MCQ):** What is the output?
```python
names = ["Ravi", "Priya", "Karan", "Ana"]
result = list(filter(lambda n: len(n) == 4, names))
print(result)
```
a) `["Ravi", "Priya", "Karan"]`
b) `["Ana"]`
c) `["Ravi"]`
d) `["Ravi", "Ana"]`

**Q9 (Open-Ended):** What is the output?
```python
calc = lambda x, y, z: x + y * z
print(calc(2, 3, 4))
```

**Q10 (Open-Ended):** What is the output?
```python
data = [{"name": "Ravi", "age": 25}, {"name": "Priya", "age": 22}]
result = sorted(data, key=lambda x: x["age"])
print(result[0]["name"])
```
