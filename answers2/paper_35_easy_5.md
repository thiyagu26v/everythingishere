# 📝 Question Paper 35 — Easy 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is string formatting in Python? Name the different ways to format strings.
2. What are Django forms? What is the difference between `Form` and `ModelForm`?
3. What is the `LIKE` operator in SQL? Give examples with `%` and `_`.
4. What is a Python lambda function? When would you use it?
5. What is the difference between `PUT` and `PATCH` in HTTP?
6. What are nested lists in Python? How do you access elements in them?
7. What does `NOT NULL` constraint mean in SQL?
8. What is a Django migration? Why is it needed?
9. What is the difference between `sorted()` and `.sort()` in Python?
10. What is an environment variable? How do you access one in Python?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python built-in function converts a value to a float?
2. What SQL command removes a specific row from a table?
3. What Django method returns a 404 if an object is not found?
4. What Python method checks if a key exists in a dictionary?
5. What HTTP method is used to partially update a resource?
6. What Python module is used to work with file paths?
7. What SQL clause specifies which table to query?
8. What DRF decorator converts a function into an API view?
9. What Python method inserts an element at a specific position in a list?
10. What does `DBMS` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a number and returns its factorial using recursion.
```
Input:  5
Output: 120

Input:  0
Output: 1
```

**Problem 2:** Write a function that takes a list of strings and returns the longest string.
```
Input:  ["cat", "elephant", "dog", "hippopotamus"]
Output: "hippopotamus"
```

**Problem 3:** Write a function that removes duplicate values from a list while maintaining order.
```
Input:  [1, 3, 2, 3, 1, 5, 2, 4]
Output: [1, 3, 2, 5, 4]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 65000  |
| 2      | Priya  | HR         | 42000  |
| 3      | Karan  | IT         | 55000  |
| 4      | Meena  | Sales      | 48000  |
| 5      | Arjun  | HR         | 70000  |

**Table: orders**
| order_id | customer_id | amount | status    |
|----------|-------------|--------|-----------|
| 1        | 101         | 5000   | pending   |
| 2        | 102         | 3000   | completed |
| 3        | 101         | 7000   | completed |
| 4        | 103         | 2000   | cancelled |
| 5        | 102         | 4000   | pending   |

**Table: products**
| product_id | name     | price |
|------------|----------|-------|
| 1          | Laptop   | 50000 |
| 2          | Mouse    | 500   |
| 3          | Keyboard | 1500  |
| 4          | Monitor  | 20000 |

**Problem 1:** Write a SQL query to find employees whose salary is above the company average.

**Problem 2:** Write a SQL query to count orders per status (pending, completed, cancelled) from the `orders` table.

**Problem 3:** Write a SQL query to find the second most expensive product.

### Part D — OOP Based Problem

Create a class `Contact` with:
- Attributes: `name`, `phone`, `email`, `group` (family/friend/work)
- Create a `ContactBook` class with:
  - Methods: `add_contact(contact)`, `search(name)`, `list_by_group(group)`, `delete_contact(name)`, `total_contacts()`
  - `search` should work with partial name matches (case-insensitive)
- Create a contact book, add 5 contacts from different groups, search for one, list by group

### Part E — Django Based Problem

Create a Django app with a `Feedback` model: `name` (CharField), `email` (EmailField), `subject` (CharField), `message` (TextField), `rating` (IntegerField, 1-5), `submitted_at` (DateTimeField auto). Write a DRF `ModelSerializer` and create a viewset that only allows POST (create) and GET (list) operations — no update or delete.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x + y for x, y in [(1, 2), (3, 4), (5, 6)]]
print(result)
```
a) `[(1, 2), (3, 4), (5, 6)]`
b) `[3, 7, 11]`
c) `[1, 3, 5]`
d) `[2, 4, 6]`

**Q2 (MCQ):** What is the output?
```python
result = [c * 3 for c in "ab"]
print(result)
```
a) `["a", "b"]`
b) `["aaa", "bbb"]`
c) `["ab", "ab", "ab"]`
d) `["a3", "b3"]`

**Q3 (MCQ):** What is the output?
```python
nums = [10, 20, 30, 40, 50]
result = [n for n in nums if n > 25]
print(result)
```
a) `[10, 20]`
b) `[30, 40, 50]`
c) `[10, 20, 25]`
d) `[25, 30, 40, 50]`

**Q4 (Open-Ended):** What is the output?
```python
result = [i ** 2 for i in range(5)]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
sentence = "I love Python"
result = [word for word in sentence.split() if len(word) > 1]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
half = lambda x: x / 2
print(half(10))
```
a) `5`
b) `5.0`
c) `2`
d) `20`

**Q7 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4]
result = list(map(lambda x: str(x), nums))
print(result)
```
a) `[1, 2, 3, 4]`
b) `["1", "2", "3", "4"]`
c) `"1234"`
d) `10`

**Q8 (MCQ):** What is the output?
```python
values = [True, False, True, False, True]
result = list(filter(lambda x: not x, values))
print(len(result))
```
a) `5`
b) `3`
c) `2`
d) `0`

**Q9 (Open-Ended):** What is the output?
```python
full_name = lambda first, last: f"{first} {last}"
print(full_name("Ravi", "Kumar"))
```

**Q10 (Open-Ended):** What is the output?
```python
words = ["banana", "apple", "cherry"]
result = sorted(words, key=lambda w: w)
print(result)
```
