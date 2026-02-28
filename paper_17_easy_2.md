# 📝 Question Paper 17 — Easy 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is indentation in Python? Why is it important?
2. What is the purpose of `views.py` in Django?
3. What is a foreign key? How is it different from a primary key?
4. What is string slicing in Python? Give an example.
5. What is the difference between `require` and `include` in Django URL patterns?
6. What are comments in SQL? How do you write single-line and multi-line comments?
7. What is a constructor in Python OOP?
8. What is the difference between frontend and backend development?
9. What is `requirements.txt` in a Python project? Why is it important?
10. What does the `len()` function do? Can it work on strings, lists, and dictionaries?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What built-in function returns the sum of all elements in a list?
2. What SQL keyword adds a new row to a table?
3. What command creates a new Django app inside a project?
4. What Python operator checks if a value exists in a list?
5. What HTTP status code means "Internal Server Error"?
6. What method converts a list to a string with a separator?
7. What SQL keyword removes a table completely?
8. What Python data type stores True or False values?
9. What Django template tag is used for if-else conditions?
10. What does `HTML` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list and returns a new list with elements in reverse order (without using `reverse()` or slicing).
```
Input:  [1, 2, 3, 4, 5]
Output: [5, 4, 3, 2, 1]
```

**Problem 2:** Write a function that takes a number and returns the sum of its digits.
```
Input:  1234
Output: 10

Input:  9087
Output: 24
```

**Problem 3:** Write a function that takes a list of strings and returns a dictionary with the string as key and its length as value.
```
Input:  ["apple", "cat", "banana"]
Output: {"apple": 5, "cat": 3, "banana": 6}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary | hire_date  |
|--------|--------|------------|--------|------------|
| 1      | Ravi   | IT         | 55000  | 2023-06-15 |
| 2      | Priya  | HR         | 38000  | 2024-01-20 |
| 3      | Karan  | Sales      | 42000  | 2023-09-10 |
| 4      | Meena  | IT         | 60000  | 2022-12-01 |

**Table: orders**
| order_id | customer_name | amount | order_date |
|----------|---------------|--------|------------|
| 1        | Ravi          | 5000   | 2024-02-10 |
| 2        | Priya         | 3000   | 2024-02-25 |
| 3        | Karan         | 8000   | 2024-01-15 |

**Problem 1:** Write a SQL query to find the minimum and maximum salary from the `employees` table.

**Problem 2:** Write a SQL query to select distinct departments from the `employees` table.

**Problem 3:** Write a SQL query to find all orders placed in the last 30 days from the `orders` table.

### Part D — OOP Based Problem

Create a class `Calculator` with:
- Methods: `add(a, b)`, `subtract(a, b)`, `multiply(a, b)`, `divide(a, b)`
- The `divide` method should handle division by zero and return an error message
- Add a `history` list that stores all operations performed as strings
- Add a `show_history()` method that prints all past calculations

### Part E — Django Based Problem

Create a Django model `Event` with fields: `name` (CharField), `description` (TextField), `date` (DateField), `location` (CharField), `max_attendees` (IntegerField). Write a function-based view that returns all upcoming events (date >= today) as a JSON response.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x ** 3 for x in [1, 2, 3]]
print(result)
```
a) `[1, 4, 9]`
b) `[1, 8, 27]`
c) `[3, 6, 9]`
d) `[1, 2, 3]`

**Q2 (MCQ):** What is the output?
```python
text = "Python3"
result = [c for c in text if c.isalpha()]
print(result)
```
a) `["P", "y", "t", "h", "o", "n", "3"]`
b) `["P", "y", "t", "h", "o", "n"]`
c) `["3"]`
d) `["Python"]`

**Q3 (MCQ):** What is the output?
```python
result = [i * "★" for i in range(1, 4)]
print(result)
```
a) `["★", "★★", "★★★"]`
b) `[1, 2, 3]`
c) `["1★", "2★", "3★"]`
d) `["★★★", "★★", "★"]`

**Q4 (Open-Ended):** What is the output?
```python
nums = [10, 20, 30, 40, 50]
result = [n for n in nums if n not in [20, 40]]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
result = [max(a, b) for a, b in [(1, 5), (8, 3), (2, 7)]]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
length = lambda s: len(s)
print(length("Python"))
```
a) `"Python"`
b) `6`
c) `"6"`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
nums = [10, 20, 30]
result = list(map(lambda x: x - 5, nums))
print(result)
```
a) `[5, 15, 25]`
b) `[15, 25, 35]`
c) `[10, 20, 30]`
d) `[50, 100, 150]`

**Q8 (MCQ):** What is the output?
```python
words = ["cat", "dog", "elephant", "ant", "bee"]
result = list(filter(lambda w: len(w) <= 3, words))
print(result)
```
a) `["elephant"]`
b) `["cat", "dog", "ant", "bee"]`
c) `["cat", "dog"]`
d) `["ant", "bee"]`

**Q9 (Open-Ended):** What is the output?
```python
maximum = lambda a, b: a if a > b else b
print(maximum(15, 20))
```

**Q10 (Open-Ended):** What is the output?
```python
items = [("pen", 10), ("book", 50), ("bag", 200)]
result = sorted(items, key=lambda x: x[1])
print(result[-1][0])
```
