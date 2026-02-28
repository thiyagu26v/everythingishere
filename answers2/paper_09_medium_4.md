# 📝 Question Paper 09 — Medium 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is method overriding in Python? Give an example.
2. Explain Django's ORM query optimization techniques (select_related, prefetch_related, only, defer).
3. What is the difference between a `PRIMARY KEY` and a `FOREIGN KEY` in SQL?
4. What are abstract classes in Python? How are they different from regular classes?
5. What is the difference between `Token` authentication and `Session` authentication in DRF?
6. How does Python's `collections` module help? Name at least 3 useful classes from it.
7. What is database denormalization? When would you use it?
8. Explain the concept of mixins in Python. How are they used in Django/DRF?
9. What is SQL injection? How do you prevent it in Django?
10. What is the difference between synchronous and asynchronous task processing?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function returns the length of a list?
2. What SQL keyword adds a constraint to an existing table?
3. What DRF mixin provides the `list()` action?
4. What Python method returns all key-value pairs of a dictionary as tuples?
5. What Django setting specifies the authentication backends?
6. What HTTP header is used to send the authentication token?
7. What SQL function returns the current date and time?
8. What Python library is used for environment variable management in Django?
9. What REST principle states that each request should contain all needed info?
10. What Django command opens an interactive Python shell with project context?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that implements binary search on a sorted list. Return the index if found, -1 otherwise.
```
Input:  [2, 5, 8, 12, 16, 23, 38], target = 16
Output: 4

Input:  [2, 5, 8, 12, 16, 23, 38], target = 10
Output: -1
```

**Problem 2:** Write a function that takes a string containing brackets `()[]{}` and checks if they are balanced.
```
Input:  "{[()]}"
Output: True

Input:  "{[(])}"
Output: False
```

**Problem 3:** Implement a `Queue` class using two stacks (lists). It should have `enqueue` and `dequeue` methods.
```
q = Queue()
q.enqueue(1)
q.enqueue(2)
q.enqueue(3)
q.dequeue()  → 1
q.dequeue()  → 2
```

**Problem 4:** Write a function that reads a CSV file and returns the data as a list of dictionaries where each dictionary represents a row.
```
# CSV file content:
# name,age,city
# Ravi,25,Chennai
# Priya,22,Mumbai

Output: [{"name": "Ravi", "age": "25", "city": "Chennai"}, {"name": "Priya", "age": "22", "city": "Mumbai"}]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: users**
| user_id | name   | email              |
|---------|--------|--------------------|
| 1       | Ravi   | ravi@gmail.com     |
| 2       | Priya  | priya@gmail.com    |
| 3       | Karan  | ravi@gmail.com     |
| 4       | Meena  | meena@yahoo.com    |
| 5       | Arjun  | priya@gmail.com    |

**Table: products**
| product_id | name     | price | category    |
|------------|----------|-------|-------------|
| 1          | Laptop   | 50000 | Electronics |
| 2          | Mouse    | 500   | Electronics |
| 3          | Notebook | 100   | Stationery  |
| 4          | Pen      | 20    | Stationery  |
| 5          | Headset  | 2000  | Electronics |

**Problem 1:** Write a SQL query to find duplicate email addresses in the `users` table and count their occurrences.

**Problem 2:** Write a SQL query to implement pagination — get rows 21 to 40 from the `products` table ordered by `price`.

**Problem 3:** Write a SQL trigger (or explain the concept) that automatically sets `updated_at` column whenever a row is updated.

### Part D — OOP Based Problem

Design a simple banking system using OOP:
- `Account` (abstract base class) with `account_number`, `owner`, `balance`
  - Abstract methods: `deposit()`, `withdraw()`, `get_interest()`
- `SavingsAccount` inherits `Account`:
  - Has `interest_rate`, withdraw limit (cannot withdraw more than 80% of balance)
  - `get_interest()` returns balance * interest_rate
- `CurrentAccount` inherits `Account`:
  - Has `overdraft_limit`, no interest
  - Can withdraw up to balance + overdraft_limit
- Demonstrate polymorphism by processing a list of mixed account types

### Part E — Django Based Problem

Build a Blog API with DRF:
- Models: `Category` (name, slug), `Post` (title, content, category as FK, author as FK to User, status with choices draft/published, created_at, updated_at)
- Custom serializer validation: title must be at least 10 characters
- Add a custom action in the viewset: `POST /posts/{id}/publish/` that changes status to "published"
- Only the author should be able to edit/delete their own posts (custom permission)

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [s.strip() for s in ["  hi  ", " bye ", "hello"]]
print(result)
```
a) `["  hi  ", " bye ", "hello"]`
b) `["hi", "bye", "hello"]`
c) `["h i", "b y e", "hello"]`
d) `["hi  ", "bye ", "hello"]`

**Q2 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = [nums[i] + nums[i+1] for i in range(len(nums)-1)]
print(result)
```
a) `[1, 2, 3, 4, 5]`
b) `[3, 5, 7, 9]`
c) `[2, 4, 6, 8]`
d) `[1, 3, 6, 10, 15]`

**Q3 (MCQ):** What is the output?
```python
result = [i * j for i in [1, 2] for j in [10, 20]]
print(result)
```
a) `[10, 20, 20, 40]`
b) `[10, 40]`
c) `[(1, 10), (2, 20)]`
d) `[11, 21, 12, 22]`

**Q4 (Open-Ended):** What is the output?
```python
data = ["Ravi:25", "Priya:30", "Karan:22"]
result = {item.split(":")[0]: int(item.split(":")[1]) for item in data}
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
nums = [4, 7, 2, 9, 1, 5]
result = [x for x in nums if x > sum(nums) / len(nums)]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
operations = {
    "add": lambda a, b: a + b,
    "sub": lambda a, b: a - b,
    "mul": lambda a, b: a * b,
}
print(operations["mul"](4, 5))
```
a) `9`
b) `20`
c) `"mul"`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
nums = ["10", "20", "30"]
result = list(map(lambda x: int(x) * 2, nums))
print(result)
```
a) `["1010", "2020", "3030"]`
b) `[20, 40, 60]`
c) `["20", "40", "60"]`
d) `Error`

**Q8 (MCQ):** What is the output?
```python
words = ["apple", "banana", "cherry", "date", "elderberry"]
result = max(words, key=lambda w: len(w))
print(result)
```
a) `"apple"`
b) `"elderberry"`
c) `"cherry"`
d) `10`

**Q9 (Open-Ended):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = list(map(lambda x: "even" if x % 2 == 0 else "odd", nums))
print(result)
```

**Q10 (Open-Ended):** What is the output?
```python
students = [("Ravi", 80, "A"), ("Priya", 92, "A+"), ("Karan", 65, "B")]
result = sorted(students, key=lambda s: (-s[1], s[0]))
print(result[0][0])
```
