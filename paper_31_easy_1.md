# 📝 Question Paper 31 — Easy 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is a variable in Python? How do you assign a value to one?
2. What is Django? Why is it called a "batteries-included" framework?
3. What is the difference between `INT` and `FLOAT` data types in SQL?
4. What is a tuple in Python? How is it different from a list?
5. What is an API endpoint? Give a simple example.
6. What are loops in Python? What is the difference between `for` and `while`?
7. What does `SELECT *` mean in SQL?
8. What is `models.py` used for in a Django app?
9. What is the difference between `append()` and `extend()` in Python lists?
10. What is a database? Name two popular relational databases.

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python built-in function returns the smallest item in a list?
2. What SQL keyword filters rows based on a condition?
3. What Django command starts a development server?
4. What Python function converts a string to an integer?
5. What HTTP method retrieves data from a server?
6. What Python method adds an element to the end of a list?
7. What SQL keyword orders results from lowest to highest?
8. What file type does DRF return by default?
9. What Python operator is used for exponentiation?
10. What does `HTTP` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of numbers and returns a list of only even numbers.
```
Input:  [1, 2, 3, 4, 5, 6, 7, 8]
Output: [2, 4, 6, 8]
```

**Problem 2:** Write a function that counts how many times each character appears in a string (ignore spaces).
```
Input:  "hello world"
Output: {"h": 1, "e": 1, "l": 3, "o": 2, "w": 1, "r": 1, "d": 1}
```

**Problem 3:** Write a function that takes a list of numbers and returns the average, rounded to 2 decimal places.
```
Input:  [10, 20, 30, 40, 50]
Output: 30.0

Input:  [7, 13, 21]
Output: 13.67
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Arjun  | IT         | 55000  |
| 2      | Asha   | HR         | 42000  |
| 3      | Ravi   | Sales      | 38000  |
| 4      | Priya  | IT         | 60000  |
| 5      | Amit   | HR         | 45000  |

**Table: products**
| product_id | name     | price | category    | stock |
|------------|----------|-------|-------------|-------|
| 1          | Laptop   | 50000 | Electronics | 10    |
| 2          | Mouse    | 500   | Electronics | 50    |
| 3          | Notebook | 100   | Stationery  | 200   |
| 4          | Pen      | 20    | Stationery  | 500   |

**Problem 1:** Write a SQL query to find all employees whose name starts with the letter 'A'.

**Problem 2:** Write a SQL query to count the total number of products in the `products` table.

**Problem 3:** Write a SQL query to find the average price of all products grouped by `category`.

### Part D — OOP Based Problem

Create a class `Pet` with:
- Attributes: `name`, `species` (dog/cat/bird), `age`, `is_vaccinated` (default False)
- Method `vaccinate()` that sets `is_vaccinated` to True
- Method `info()` that returns a formatted string with all details
- Create 3 pets, vaccinate one, and display info for all

### Part E — Django Based Problem

Create a Django model `Product` with fields: `name` (CharField), `description` (TextField), `price` (DecimalField), `stock` (IntegerField), `created_at` (DateTimeField). Register it in admin and write a simple view that returns all products as JSON.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x + 10 for x in [1, 2, 3]]
print(result)
```
a) `[1, 2, 3]`
b) `[11, 12, 13]`
c) `[10, 20, 30]`
d) `[10, 10, 10]`

**Q2 (MCQ):** What is the output?
```python
result = [x for x in range(1, 11) if x % 5 == 0]
print(result)
```
a) `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`
b) `[5, 10]`
c) `[0, 5, 10]`
d) `[5]`

**Q3 (MCQ):** What is the output?
```python
words = ["cat", "dog", "fish"]
result = [w.upper() for w in words]
print(result)
```
a) `["cat", "dog", "fish"]`
b) `["CAT", "DOG", "FISH"]`
c) `["Cat", "Dog", "Fish"]`
d) `["C", "D", "F"]`

**Q4 (Open-Ended):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = [n * n for n in nums]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
result = [str(x) for x in [10, 20, 30]]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
double = lambda x: x * 2
print(double(5))
```
a) `5`
b) `10`
c) `"55"`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
nums = [4, 7, 2, 9]
result = list(map(lambda x: x + 1, nums))
print(result)
```
a) `[4, 7, 2, 9]`
b) `[5, 8, 3, 10]`
c) `[3, 6, 1, 8]`
d) `1`

**Q8 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5, 6]
result = list(filter(lambda x: x > 3, nums))
print(result)
```
a) `[1, 2, 3]`
b) `[4, 5, 6]`
c) `[3, 4, 5, 6]`
d) `True`

**Q9 (Open-Ended):** What is the output?
```python
square = lambda n: n ** 2
print(square(4))
```

**Q10 (Open-Ended):** What is the output?
```python
nums = [5, 2, 8, 1]
result = sorted(nums, key=lambda x: x)
print(result)
```
