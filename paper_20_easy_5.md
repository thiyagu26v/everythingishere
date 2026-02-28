# 📝 Question Paper 20 — Easy 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `try-except` and `try-except-finally` in Python?
2. What is Django's template inheritance? How does `{% extends %}` work?
3. What are constraints in SQL? Name the main types.
4. What is a Python module? How do you create and import one?
5. What is the difference between `ForeignKey` and `OneToOneField` in Django?
6. What are aggregate functions in SQL? Name at least 4 with examples.
7. What is method overriding in Python? Give a simple example.
8. What is status code 201 vs 200 in HTTP?
9. What is the difference between `range()` and `enumerate()` in Python?
10. What is `CORS`? Why does it matter in web development?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function returns the data type of a variable?
2. What SQL clause is used to limit the number of results?
3. What Django command creates a superuser?
4. What Python keyword handles multiple conditions after `if`?
5. What HTTP method is considered idempotent and used to replace a resource?
6. What Python module is used for generating random numbers?
7. What SQL keyword ensures a column has unique values?
8. What Python function checks if a variable is an instance of a class?
9. What DRF response class is used to return JSON data?
10. What does `CRUD` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of dictionaries with `name` and `age`, and returns a list of names sorted by age (youngest first).
```
Input:  [{"name": "Ravi", "age": 25}, {"name": "Priya", "age": 20}, {"name": "Karan", "age": 22}]
Output: ["Priya", "Karan", "Ravi"]
```

**Problem 2:** Write a function that takes a sentence and returns the word that appears the most.
```
Input:  "the cat sat on the mat the cat"
Output: "the"
```

**Problem 3:** Write a function that generates a multiplication table for a given number as a list of strings.
```
Input:  5
Output: ["5 x 1 = 5", "5 x 2 = 10", "5 x 3 = 15", ..., "5 x 10 = 50"]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary | hire_date  |
|--------|--------|------------|--------|------------|
| 1      | Ravi   | IT         | 55000  | 2024-03-10 |
| 2      | Priya  | HR         | 42000  | 2024-06-15 |
| 3      | Karan  | IT         | 48000  | 2023-11-20 |
| 4      | Meena  | Sales      | 35000  | 2024-01-05 |

**Table: orders**
| order_id | customer_id | amount | payment_status | status    |
|----------|-------------|--------|----------------|-----------|
| 1        | 101         | 5000   | success        | delivered |
| 2        | 102         | 3000   | failed         | pending   |
| 3        | 103         | 7000   | success        | shipped   |
| 4        | 104         | 2000   | failed         | pending   |

**Problem 1:** Write a SQL query to find employees who were hired in 2024 and have a salary greater than 40000.

**Problem 2:** Write a SQL query to list all tables in a database (use the appropriate command for MySQL or PostgreSQL).

**Problem 3:** Write a SQL query to update the `status` of all orders to 'cancelled' where `payment_status` is 'failed'.

### Part D — OOP Based Problem

Create a class `ShoppingItem` with attributes `name`, `price`, `quantity`. Create a class `ShoppingList` with:
- Methods: `add_item(name, price, qty)`, `remove_item(name)`, `update_quantity(name, new_qty)`, `total_cost()`, `display()`
- `total_cost()` returns the sum of price × quantity for all items
- Handle edge cases: removing non-existent items, negative quantities
- Create a list, add 4 items, update one quantity, remove one, show total

### Part E — Django Based Problem

Create a simple blog with DRF:
- Model: `Article` with fields: `title`, `body`, `author_name`, `category` (CharField), `published` (BooleanField), `created_at`
- Create serializer and viewset
- Add a URL endpoint `/api/articles/`
- The API should only return published articles by default

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x.split(",") for x in ["a,b", "c,d"]]
print(result)
```
a) `["a", "b", "c", "d"]`
b) `[["a", "b"], ["c", "d"]]`
c) `["a,b", "c,d"]`
d) `[("a", "b"), ("c", "d")]`

**Q2 (MCQ):** What is the output?
```python
result = [i ** 2 for i in range(-3, 4)]
print(result)
```
a) `[9, 4, 1, 0, 1, 4, 9]`
b) `[-9, -4, -1, 0, 1, 4, 9]`
c) `[0, 1, 4, 9]`
d) `[9, 4, 1]`

**Q3 (MCQ):** What is the output?
```python
words = ["abc", "de", "f", "ghij"]
result = [w for w in words if len(w) % 2 == 0]
print(result)
```
a) `["abc", "f"]`
b) `["de", "ghij"]`
c) `["abc", "ghij"]`
d) `["de", "f"]`

**Q4 (Open-Ended):** What is the output?
```python
result = [chr(65 + i) for i in range(5)]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = [sum(nums[:i+1]) for i in range(len(nums))]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
repeat = lambda s, n: s * n
print(repeat("ab", 3))
```
a) `"ab3"`
b) `"ababab"`
c) `"aabbcc"`
d) `"ab ab ab"`

**Q7 (MCQ):** What is the output?
```python
data = [True, False, True, True, False]
result = list(filter(lambda x: x, data))
print(len(result))
```
a) `5`
b) `3`
c) `2`
d) `0`

**Q8 (MCQ):** What is the output?
```python
nums = [4, 1, 7, 3]
result = list(map(lambda x: f"Item-{x}", nums))
print(result[2])
```
a) `"Item-4"`
b) `"Item-7"`
c) `"Item-1"`
d) `7`

**Q9 (Open-Ended):** What is the output?
```python
check = lambda x: "even" if x % 2 == 0 else "odd"
print(check(7))
print(check(4))
```

**Q10 (Open-Ended):** What is the output?
```python
people = [{"name": "A", "age": 30}, {"name": "B", "age": 20}, {"name": "C", "age": 25}]
youngest = min(people, key=lambda p: p["age"])
print(youngest["name"])
```
