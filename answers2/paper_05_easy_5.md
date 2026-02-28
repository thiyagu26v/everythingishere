# 📝 Question Paper 05 — Easy 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `break`, `continue`, and `pass` in Python?
2. What is the purpose of `serializers.py` in DRF?
3. What are aggregate functions in SQL? Name at least 3.
4. What is a lambda function in Python?
5. Explain the MVC/MVT architecture. How does Django follow it?
6. What is the difference between `INNER JOIN` and `LEFT JOIN`?
7. What is `self` in Python? Why is it used in class methods?
8. What is the difference between authentication and authorization?
9. What is a Python module vs a Python package?
10. What are Django templates? What is the template engine?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python keyword is used to exit a loop early?
2. What SQL keyword is used to create a new table?
3. What DRF class is used to create API views easily?
4. What Python function opens a file for reading or writing?
5. What Django template tag is used for loops?
6. What is the default content type for a DRF response?
7. What Python method joins list elements into a string?
8. What SQL constraint ensures all values in a column are unique?
9. What does `WSGI` stand for?
10. What Python keyword is used for inheritance?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a number `n` and returns the factorial of `n` using a loop (not recursion).
```
Input:  5
Output: 120

Input:  0
Output: 1
```

**Problem 2:** Write a program that takes a list of numbers and separates them into two lists: one for odd numbers and one for even numbers.
```
Input:  [1, 2, 3, 4, 5, 6, 7, 8]
Output: odd = [1, 3, 5, 7], even = [2, 4, 6, 8]
```

**Problem 3:** Write a function that flattens a nested list. Example: `[[1,2],[3,[4,5]]]` → `[1,2,3,4,5]`
```
Input:  [[1, 2], [3, [4, 5]]]
Output: [1, 2, 3, 4, 5]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary | hire_date  |
|--------|--------|------------|--------|------------|
| 1      | Ravi   | IT         | 60000  | 2023-04-10 |
| 2      | Priya  | HR         | 55000  | 2024-01-15 |
| 3      | Karan  | IT         | 60000  | 2024-07-20 |
| 4      | Meena  | Sales      | 48000  | 2022-09-05 |
| 5      | Arjun  | Finance    | 52000  | 2024-11-12 |

**Problem 1:** Write a SQL query to find the second highest salary from the `employees` table.

**Problem 2:** Write a SQL query to find employees who were hired in the year 2024.

**Problem 3:** Write a SQL query to create a table called `orders` with columns: `order_id` (INT, PRIMARY KEY), `customer_name` (VARCHAR), `amount` (DECIMAL), `order_date` (DATE).

### Part D — OOP Based Problem

Create a class `Animal` with a method `speak()`. Create two child classes `Dog` and `Cat` that inherit from `Animal` and override the `speak()` method. `Dog` should return "Woof!" and `Cat` should return "Meow!". Demonstrate polymorphism by calling `speak()` on both objects.

### Part E — Django Based Problem

Set up a DRF `ModelViewSet` for a `Task` model with fields: `title`, `description`, `is_completed`, `created_at`. Register the viewset with a router and include the router URLs in `urls.py`.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x.replace("a", "@") for x in ["apple", "banana", "cat"]]
print(result)
```
a) `["@pple", "b@n@n@", "c@t"]`
b) `["apple", "banana", "cat"]`
c) `["pple", "bnn", "ct"]`
d) `["Apple", "Banana", "Cat"]`

**Q2 (MCQ):** What is the output?
```python
matrix = [[1, 2], [3, 4], [5, 6]]
result = [row[0] for row in matrix]
print(result)
```
a) `[[1, 2], [3, 4], [5, 6]]`
b) `[1, 3, 5]`
c) `[2, 4, 6]`
d) `[1, 2, 3]`

**Q3 (MCQ):** What is the output?
```python
result = [i for i in range(5, 0, -1)]
print(result)
```
a) `[0, 1, 2, 3, 4, 5]`
b) `[5, 4, 3, 2, 1]`
c) `[5, 4, 3, 2, 1, 0]`
d) `[1, 2, 3, 4, 5]`

**Q4 (Open-Ended):** What is the output?
```python
result = ["Even" if x % 2 == 0 else "Odd" for x in [1, 2, 3, 4]]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
sentence = "hello world python"
result = [word.capitalize() for word in sentence.split()]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
full_name = lambda first, last: f"{first} {last}"
print(full_name("Ravi", "Kumar"))
```
a) `"RaviKumar"`
b) `"Ravi Kumar"`
c) `"Kumar Ravi"`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
nums = [10, 20, 30, 40]
result = list(map(lambda x: x // 10, nums))
print(result)
```
a) `[1, 2, 3, 4]`
b) `[10, 20, 30, 40]`
c) `[0, 0, 0, 0]`
d) `[100, 200, 300, 400]`

**Q8 (MCQ):** What is the output?
```python
words = ["python", "java", "go", "rust", "c"]
result = list(filter(lambda w: len(w) >= 4, words))
print(result)
```
a) `["python", "java", "rust"]`
b) `["go", "c"]`
c) `["python", "java", "go", "rust", "c"]`
d) `["python", "java"]`

**Q9 (Open-Ended):** What is the output?
```python
ops = [lambda x: x + 1, lambda x: x * 2, lambda x: x ** 2]
print(ops[1](5))
```

**Q10 (Open-Ended):** What is the output?
```python
students = [("Ravi", 85), ("Priya", 92), ("Karan", 78)]
result = sorted(students, key=lambda s: s[1], reverse=True)
print(result[0])
```
