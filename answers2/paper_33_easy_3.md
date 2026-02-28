# 📝 Question Paper 33 — Easy 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What are Python comments? How do you write single-line and multi-line comments?
2. What is the `manage.py` file in Django? Name 3 commands it supports.
3. What is a SQL `JOIN`? Why do we use it?
4. What is the difference between a list and a set in Python?
5. What is Postman? How do developers use it?
6. What is type casting in Python? Give examples.
7. What does `LIMIT` do in SQL?
8. What is the difference between `render()` and `redirect()` in Django?
9. What is scope in Python? Explain local and global scope.
10. What is the difference between a library, framework, and package?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method removes an element by value from a list?
2. What SQL keyword creates a new table?
3. What Django file defines URL patterns for an app?
4. What Python function returns the length of a string?
5. What HTTP method is used to delete a resource?
6. What Python keyword is used to import a module?
7. What SQL function calculates the average of a column?
8. What DRF status code constant represents "200 OK"?
9. What Python method replaces part of a string with another string?
10. What does `IDE` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a number and checks if it is a palindrome.
```
Input:  121
Output: True

Input:  123
Output: False
```

**Problem 2:** Write a function that merges two dictionaries. If a key exists in both, keep the larger value.
```
Input:  {"a": 5, "b": 10}, {"b": 3, "c": 7}
Output: {"a": 5, "b": 10, "c": 7}
```

**Problem 3:** Write a function that takes a list of names and returns a dictionary grouping them by their first letter.
```
Input:  ["Ravi", "Priya", "Rahul", "Pooja", "Karan"]
Output: {"R": ["Ravi", "Rahul"], "P": ["Priya", "Pooja"], "K": ["Karan"]}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary | job_title  |
|--------|--------|------------|--------|------------|
| 1      | Ravi   | IT         | 55000  | Developer  |
| 2      | Priya  | HR         | 42000  | Recruiter  |
| 3      | Karan  | IT         | 60000  | Developer  |
| 4      | Meena  | Sales      | 48000  | Executive  |
| 5      | Arjun  | HR         | 45000  | Manager    |

**Problem 1:** Write a SQL query to create a table `students` with columns: `id` (INT, PRIMARY KEY, AUTO_INCREMENT), `name` (VARCHAR), `age` (INT), `grade` (CHAR).

**Problem 2:** Write a SQL query to find employees who have the same job title as 'Ravi'.

**Problem 3:** Write a SQL query to find the total salary expense per department from the `employees` table.

### Part D — OOP Based Problem

Create a class `Rectangle` with:
- Attributes: `width`, `height`
- Methods: `area()`, `perimeter()`, `is_square()` (returns True if width == height)
- Create a subclass `Square` that takes only one side length
- Create 2 rectangles and 1 square, display their area and perimeter

### Part E — Django Based Problem

Create a Django model `Review` with fields: `product_name` (CharField), `reviewer_name` (CharField), `rating` (IntegerField, 1-5), `comment` (TextField), `created_at` (DateTimeField). Write a view that returns the average rating for a given product name passed as a URL parameter.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x // 2 for x in [10, 15, 20, 25]]
print(result)
```
a) `[5.0, 7.5, 10.0, 12.5]`
b) `[5, 7, 10, 12]`
c) `[20, 30, 40, 50]`
d) `[2, 2, 2, 2]`

**Q2 (MCQ):** What is the output?
```python
result = ["yes" if x > 0 else "no" for x in [-1, 0, 1, 2]]
print(result)
```
a) `[-1, 0, 1, 2]`
b) `["no", "no", "yes", "yes"]`
c) `["yes", "yes", "yes", "yes"]`
d) `[False, False, True, True]`

**Q3 (MCQ):** What is the output?
```python
result = [len(s) for s in ["a", "bb", "ccc"]]
print(result)
```
a) `["a", "bb", "ccc"]`
b) `[1, 2, 3]`
c) `[1, 1, 1]`
d) `3`

**Q4 (Open-Ended):** What is the output?
```python
result = [x for x in range(10) if x % 2 != 0]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
names = ["Alice", "Bob", "Charlie"]
result = [n.lower() for n in names]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
is_even = lambda x: x % 2 == 0
print(is_even(4))
print(is_even(7))
```
a) `True` then `True`
b) `True` then `False`
c) `False` then `True`
d) `0` then `1`

**Q7 (MCQ):** What is the output?
```python
nums = [10, 20, 30]
result = list(map(lambda x: x // 10, nums))
print(result)
```
a) `[10, 20, 30]`
b) `[1, 2, 3]`
c) `[0, 0, 0]`
d) `[100, 200, 300]`

**Q8 (MCQ):** What is the output?
```python
words = ["hi", "hello", "hey", "h"]
result = list(filter(lambda w: len(w) > 2, words))
print(result)
```
a) `["hi", "h"]`
b) `["hello", "hey"]`
c) `["hi", "hello", "hey", "h"]`
d) `["hello"]`

**Q9 (Open-Ended):** What is the output?
```python
multiply = lambda x, y: x * y
print(multiply(6, 7))
```

**Q10 (Open-Ended):** What is the output?
```python
data = [("Ravi", 25), ("Priya", 22), ("Karan", 28)]
result = sorted(data, key=lambda x: x[1])
print(result[0][0])
```
