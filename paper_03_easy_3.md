# 📝 Question Paper 03 — Easy 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between a function and a method in Python?
2. What is `manage.py` in Django?
3. What are the different types of SQL joins? Explain briefly.
4. What is list comprehension in Python? Give a simple example verbally.
5. What is the purpose of `models.py` in Django?
6. What is the difference between `CHAR` and `VARCHAR` in SQL?
7. What is `__init__` method in Python? Why is it used?
8. What is serialization in the context of DRF?
9. What is the difference between `while` loop and `for` loop?
10. What is CRUD? What does each letter stand for?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python keyword is used to import a module?
2. What SQL clause limits the number of rows returned?
3. What Django file defines database models?
4. What built-in function converts a string to an integer in Python?
5. What HTTP method is typically used to delete a resource?
6. What Python method removes an item from a list by value?
7. What does `CSRF` stand for?
8. What SQL keyword is used to update existing records?
9. What is the file name for Django URL configuration?
10. What Python keyword creates a generator?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a number and returns `True` if it's a prime number, `False` otherwise.
```
Input:  7
Output: True

Input:  10
Output: False
```

**Problem 2:** Write a program that counts the frequency of each character in a given string and returns it as a dictionary.
```
Input:  "banana"
Output: {"b": 1, "a": 3, "n": 2}
```

**Problem 3:** Write a function that takes a list of integers and returns a new list with duplicates removed (without using `set()`).
```
Input:  [1, 2, 2, 3, 4, 4, 5]
Output: [1, 2, 3, 4, 5]
```

### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 40000  |
| 2      | Priya  | HR         | 35000  |
| 3      | Karan  | Sales      | 42000  |
| 4      | Anita  | HR         | 38000  |
| 5      | Suresh | IT         | 50000  |

**Problem 1:** Write a SQL query to insert a new row into the `employees` table with values for `name`, `department`, and `salary`.

**Problem 2:** Write a SQL query to update the salary of an employee named 'Ravi' to 45000.

**Problem 3:** Write a SQL query to delete all employees from the `employees` table who belong to the `'HR'` department.

### Part D — OOP Based Problem

Create a class `Rectangle` with:
- Attributes: `length`, `width`
- Methods: `area()` and `perimeter()`
- Add a `__str__` method that returns a readable description of the rectangle
- Create 2 rectangle objects and print their area and perimeter

### Part E — Django Based Problem

Create a Django view (function-based) that returns a JSON response containing a list of 3 sample book titles. Map this view to the URL `/api/books/`.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x + 1 for x in [10, 20, 30]]
print(result)
```
a) `[10, 20, 30]`
b) `[11, 21, 31]`
c) `[9, 19, 29]`
d) `[20, 40, 60]`

**Q2 (MCQ):** What is the output?
```python
result = [c for c in "Python" if c.isupper()]
print(result)
```
a) `["P"]`
b) `["p", "y", "t", "h", "o", "n"]`
c) `["Python"]`
d) `["P", "Y", "T", "H", "O", "N"]`

**Q3 (MCQ):** What is the output?
```python
result = [x * 3 for x in range(4)]
print(result)
```
a) `[3, 6, 9, 12]`
b) `[0, 3, 6, 9]`
c) `[1, 3, 6, 9]`
d) `[0, 1, 2, 3]`

**Q4 (Open-Ended):** What is the output?
```python
result = [word.lower() for word in ["HELLO", "WORLD"]]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
nums = [5, 10, 15, 20, 25]
result = [n // 5 for n in nums]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
greet = lambda name: "Hello " + name
print(greet("Ravi"))
```
a) `"Hello"`
b) `"Hello Ravi"`
c) `"Ravi Hello"`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
nums = [3, 1, 4, 1, 5]
result = list(map(lambda x: x * x, nums))
print(result)
```
a) `[3, 1, 4, 1, 5]`
b) `[6, 2, 8, 2, 10]`
c) `[9, 1, 16, 1, 25]`
d) `[1, 1, 3, 4, 5]`

**Q8 (MCQ):** What is the output?
```python
words = ["hi", "hello", "hey", "howdy"]
result = list(filter(lambda w: len(w) > 3, words))
print(result)
```
a) `["hi", "hey"]`
b) `["hello", "howdy"]`
c) `["hi", "hello", "hey", "howdy"]`
d) `["hello", "hey", "howdy"]`

**Q9 (Open-Ended):** What is the output?
```python
power = lambda base, exp: base ** exp
print(power(2, 5))
```

**Q10 (Open-Ended):** What is the output?
```python
nums = [5, 2, 8, 1, 9]
result = sorted(nums, key=lambda x: -x)
print(result)
```
