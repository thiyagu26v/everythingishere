# 📝 Question Paper 32 — Easy 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What are Python's built-in data types? Name at least 6.
2. What is the purpose of `settings.py` in Django?
3. What is the difference between `INSERT` and `UPDATE` in SQL?
4. What is a function parameter vs an argument in Python?
5. What is a REST API? What makes an API "RESTful"?
6. What is a boolean value in Python? Give examples of truthy and falsy values.
7. What does `DISTINCT` do in a SQL query?
8. What is the Django template language? How do you display a variable in a template?
9. What is string concatenation? How do you do it in Python?
10. What is the difference between `=` and `==` in Python?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method checks if a string ends with a specific suffix?
2. What SQL clause groups rows with the same values?
3. What Django command creates a new project?
4. What Python data structure uses key-value pairs?
5. What HTTP status code means "Page Not Found"?
6. What Python function converts a list to a set?
7. What SQL function returns the total number of rows?
8. What Django template tag creates a for loop?
9. What Python keyword skips the current iteration of a loop?
10. What does `JSON` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes two lists and returns a list of elements that are common to both.
```
Input:  [1, 2, 3, 4, 5], [3, 4, 5, 6, 7]
Output: [3, 4, 5]
```

**Problem 2:** Write a function that checks if a given number is a perfect square.
```
Input:  25
Output: True

Input:  18
Output: False
```

**Problem 3:** Write a function that takes a dictionary of student names and their marks, and returns the name of the student with the highest marks.
```
Input:  {"Ravi": 85, "Priya": 92, "Karan": 78}
Output: "Priya"
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: products**
| product_id | name     | price | stock |
|------------|----------|-------|-------|
| 1          | Laptop   | 50000 | 10    |
| 2          | Mouse    | 500   | 50    |
| 3          | Keyboard | 1500  | 30    |

**Table: orders**
| order_id | customer_id | amount | order_date | status    |
|----------|-------------|--------|------------|-----------|
| 1        | 101         | 5000   | 2024-01-10 | completed |
| 2        | 102         | 3000   | 2024-03-15 | pending   |
| 3        | 101         | 7000   | 2024-05-01 | completed |
| 4        | 103         | 2000   | 2024-06-20 | cancelled |

**Table: logs**
| log_id | message      | created_at |
|--------|--------------|------------|
| 1      | User login   | 2024-01-01 |
| 2      | Error 500    | 2023-10-15 |
| 3      | Page viewed  | 2024-02-20 |

**Problem 1:** Write a SQL query to update the price of a product named 'Laptop' to 55000.

**Problem 2:** Write a SQL query to find all orders placed between '2024-01-01' and '2024-06-30'.

**Problem 3:** Write a SQL query to delete all records from the `logs` table where `created_at` is older than 90 days.

### Part D — OOP Based Problem

Create a class `BankAccount` with:
- Attributes: `owner`, `balance` (default 0)
- Methods: `deposit(amount)`, `withdraw(amount)`, `get_balance()`
- The `withdraw` method should not allow balance to go below 0
- Method `__str__` that returns "Owner: X, Balance: Y"
- Create 2 accounts, do some transactions, and display balances

### Part E — Django Based Problem

Create a DRF serializer and API endpoint for a `Task` model with fields: `title` (CharField), `description` (TextField), `is_completed` (BooleanField, default False), `due_date` (DateField). Use a `ModelViewSet` and register URLs with a router.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x - 1 for x in [5, 10, 15]]
print(result)
```
a) `[5, 10, 15]`
b) `[4, 9, 14]`
c) `[6, 11, 16]`
d) `[1, 1, 1]`

**Q2 (MCQ):** What is the output?
```python
result = [x for x in [1, 2, 3, 4, 5] if x < 4]
print(result)
```
a) `[4, 5]`
b) `[1, 2, 3]`
c) `[1, 2, 3, 4]`
d) `[]`

**Q3 (MCQ):** What is the output?
```python
names = ["ravi", "priya", "karan"]
result = [n[0] for n in names]
print(result)
```
a) `["ravi", "priya", "karan"]`
b) `["r", "p", "k"]`
c) `["R", "P", "K"]`
d) `[0, 0, 0]`

**Q4 (Open-Ended):** What is the output?
```python
result = [i * 3 for i in range(1, 5)]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
fruits = ["apple", "banana", "cherry"]
result = [f"{i+1}. {f}" for i, f in enumerate(fruits)]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
add = lambda a, b: a + b
print(add(3, 7))
```
a) `37`
b) `10`
c) `"37"`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
words = ["hello", "world"]
result = list(map(lambda w: len(w), words))
print(result)
```
a) `["hello", "world"]`
b) `[5, 5]`
c) `10`
d) `["h", "w"]`

**Q8 (MCQ):** What is the output?
```python
nums = [0, 1, 2, 0, 3, 0]
result = list(filter(lambda x: x != 0, nums))
print(result)
```
a) `[0, 0, 0]`
b) `[1, 2, 3]`
c) `6`
d) `[0, 1, 2, 0, 3, 0]`

**Q9 (Open-Ended):** What is the output?
```python
greet = lambda name: f"Hello, {name}!"
print(greet("Python"))
```

**Q10 (Open-Ended):** What is the output?
```python
nums = [10, 5, 20, 15]
biggest = max(nums, key=lambda x: x)
print(biggest)
```
