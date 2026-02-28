# 📝 Question Paper 01 — Easy 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is Python? Why is it popular for backend development?
2. What are the basic data types in Python? Name at least 5.
3. What is the difference between a list and a tuple?
4. What is a dictionary in Python? Give a simple use case.
5. What is Django? Why do developers use it?
6. What does SQL stand for? What is it used for?
7. What is a primary key in a database?
8. What is the difference between `GET` and `POST` HTTP methods?
9. What is an API? Explain in simple terms.
10. What is the difference between `==` and `is` in Python?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What keyword is used to define a function in Python?
2. What built-in function returns the length of a list?
3. What does `pip` stand for in Python?
4. What file extension do Python files use?
5. In Django, what command creates a new project?
6. What SQL keyword is used to retrieve data from a table?
7. What does DRF stand for?
8. What symbol is used for single-line comments in Python?
9. What method is used to add an element to the end of a list?
10. In SQL, what keyword is used to filter rows?

### Part B — Python Live Coding Problems

**Problem 1:** Write a Python function that takes a list of numbers and returns the sum of all even numbers.
```
Input:  [1, 2, 3, 4, 5, 6]
Output: 12
```

**Problem 2:** Write a Python program that prints numbers from 1 to 20. For multiples of 3, print "Fizz" instead of the number.
```
Output: 1, 2, Fizz, 4, 5, Fizz, 7, 8, Fizz, 10, 11, Fizz, 13, 14, Fizz, 16, 17, Fizz, 19, 20
```

**Problem 3:** Write a function that takes a string and returns it reversed.
```
Input:  "hello"
Output: "olleh"
```

### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name   | department | salary | hire_date  |
|--------|--------|------------|--------|------------|
| 1      | Ravi   | IT         | 45000  | 2023-01-15 |
| 2      | Priya  | HR         | 35000  | 2023-03-20 |
| 3      | Karan  | IT         | 55000  | 2024-06-10 |
| 4      | Anita  | Sales      | 28000  | 2022-11-05 |
| 5      | Suresh | HR         | 32000  | 2024-02-14 |

**Problem 1:** Write a SQL query to select all columns from the `employees` table.

**Problem 2:** Write a SQL query to find all employees whose `salary` is greater than 30000.

**Problem 3:** Write a SQL query to count the total number of rows in the `employees` table.

### Part D — OOP Based Problem

Create a Python class called `Student` with the following:
- Attributes: `name`, `age`, `grade`
- A method `display_info()` that prints the student's details in a readable format
- Create 2 objects of this class and call the method

### Part E — Django Based Problem

Create a new Django project called `myshop`. Inside it, create an app called `products`. Define a model `Product` with fields: `name` (CharField), `price` (DecimalField), and `in_stock` (BooleanField). Register this model in the admin panel.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x * 2 for x in [1, 2, 3, 4]]
print(result)
```
a) `[1, 2, 3, 4]`
b) `[2, 4, 6, 8]`
c) `[1, 4, 9, 16]`
d) `[3, 4, 5, 6]`

**Q2 (MCQ):** What is the output?
```python
result = [x for x in range(10) if x % 2 == 0]
print(result)
```
a) `[1, 3, 5, 7, 9]`
b) `[0, 2, 4, 6, 8]`
c) `[2, 4, 6, 8, 10]`
d) `[0, 1, 2, 3, 4]`

**Q3 (MCQ):** What is the output?
```python
words = ["hello", "world", "python"]
result = [w.upper() for w in words]
print(result)
```
a) `["hello", "world", "python"]`
b) `["Hello", "World", "Python"]`
c) `["HELLO", "WORLD", "PYTHON"]`
d) `["h", "w", "p"]`

**Q4 (Open-Ended):** What is the output?
```python
result = [i ** 2 for i in range(1, 6)]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
names = ["Ravi", "Priya", "Karan"]
result = [name[0] for name in names]
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
c) `25`
d) `7`

**Q7 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = list(map(lambda x: x + 10, nums))
print(result)
```
a) `[1, 2, 3, 4, 5]`
b) `[10, 20, 30, 40, 50]`
c) `[11, 12, 13, 14, 15]`
d) `[2, 3, 4, 5, 6]`

**Q8 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5, 6]
result = list(filter(lambda x: x > 3, nums))
print(result)
```
a) `[1, 2, 3]`
b) `[4, 5, 6]`
c) `[3, 4, 5, 6]`
d) `[True, True, True]`

**Q9 (Open-Ended):** What is the output?
```python
add = lambda a, b: a + b
print(add(3, 7))
```

**Q10 (Open-Ended):** What is the output?
```python
names = ["Karan", "Arjun", "Priya"]
result = sorted(names, key=lambda x: len(x))
print(result)
```
