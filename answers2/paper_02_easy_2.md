# 📝 Question Paper 02 — Easy 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between a mutable and immutable object in Python? Give examples.
2. What is a virtual environment in Python? Why do we use it?
3. Explain what `urls.py` does in a Django project.
4. What is a foreign key in a database?
5. What are Python decorators? Give a basic idea.
6. What is the difference between `NULL` and `NOT NULL` in SQL?
7. What is the purpose of `settings.py` in Django?
8. What is a REST API?
9. What is the difference between `append()` and `extend()` in Python lists?
10. What are HTTP status codes? Name a few common ones.

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What keyword is used to create a class in Python?
2. What Django command runs the development server?
3. In SQL, what keyword is used to sort results?
4. What is the default port number for Django's development server?
5. What Python keyword is used to handle exceptions?
6. What SQL keyword removes duplicate rows from results?
7. What does `ORM` stand for?
8. What method converts a string to lowercase in Python?
9. What Django command applies database migrations?
10. What data structure uses key-value pairs in Python?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of numbers and returns the largest number without using the `max()` function.
```
Input:  [3, 7, 2, 9, 5]
Output: 9
```

**Problem 2:** Write a program that checks whether a given string is a palindrome or not.
```
Input:  "madam"
Output: True

Input:  "hello"
Output: False
```

**Problem 3:** Write a function that takes two lists and returns a new list containing only the common elements.
```
Input:  [1, 2, 3, 4], [3, 4, 5, 6]
Output: [3, 4]
```

### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name    | department | salary | hire_date  |
|--------|---------|------------|--------|------------|
| 1      | Ravi    | IT         | 50000  | 2023-01-15 |
| 2      | Priya   | HR         | 38000  | 2023-05-10 |
| 3      | Karan   | IT         | 62000  | 2022-08-20 |
| 4      | Meena   | Finance    | 45000  | 2024-01-12 |
| 5      | Arjun   | IT         | 55000  | 2023-11-30 |
| 6      | Divya   | HR         | 40000  | 2024-03-18 |

**Problem 1:** Write a SQL query to select the `name` and `salary` of employees from the `employees` table, ordered by salary in descending order.

**Problem 2:** Write a SQL query to find employees who work in the `'IT'` department.

**Problem 3:** Write a SQL query to get the average salary of all employees.

### Part D — OOP Based Problem

Create a class `BankAccount` with:
- Attributes: `account_holder`, `balance`
- Methods: `deposit(amount)`, `withdraw(amount)`, `check_balance()`
- The withdraw method should not allow withdrawal if the amount exceeds the balance
- Create an object, deposit 5000, withdraw 2000, and check the balance

### Part E — Django Based Problem

In an existing Django project, create an app called `blog`. Define a model `Post` with fields: `title` (CharField), `content` (TextField), `created_at` (DateTimeField with auto_now_add). Create and apply the migration for this model.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x ** 2 for x in range(5)]
print(result)
```
a) `[1, 4, 9, 16, 25]`
b) `[0, 1, 4, 9, 16]`
c) `[0, 2, 4, 6, 8]`
d) `[0, 1, 2, 3, 4]`

**Q2 (MCQ):** What is the output?
```python
result = [x for x in "hello" if x not in "aeiou"]
print(result)
```
a) `["h", "e", "l", "l", "o"]`
b) `["e", "o"]`
c) `["h", "l", "l"]`
d) `["hello"]`

**Q3 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = [n * n for n in nums if n % 2 != 0]
print(result)
```
a) `[1, 9, 25]`
b) `[4, 16]`
c) `[1, 4, 9, 16, 25]`
d) `[2, 4]`

**Q4 (Open-Ended):** What is the output?
```python
result = [len(word) for word in ["cat", "elephant", "dog"]]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
result = [i for i in range(1, 11) if i % 3 == 0]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
square = lambda x: x ** 2
print(square(4))
```
a) `4`
b) `8`
c) `16`
d) `2`

**Q7 (MCQ):** What is the output?
```python
result = list(map(lambda x: x.upper(), ["hi", "bye"]))
print(result)
```
a) `["hi", "bye"]`
b) `["HI", "BYE"]`
c) `["Hi", "Bye"]`
d) `["h", "b"]`

**Q8 (MCQ):** What is the output?
```python
nums = [10, 25, 30, 45, 50]
result = list(filter(lambda x: x >= 30, nums))
print(result)
```
a) `[10, 25]`
b) `[30, 45, 50]`
c) `[10, 25, 30]`
d) `[45, 50]`

**Q9 (Open-Ended):** What is the output?
```python
multiply = lambda a, b: a * b
print(multiply(4, 5))
```

**Q10 (Open-Ended):** What is the output?
```python
words = ["banana", "apple", "cherry"]
result = sorted(words, key=lambda x: x[-1])
print(result)
```
