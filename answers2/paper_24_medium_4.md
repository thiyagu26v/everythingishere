# 📝 Question Paper 24 — Medium 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What are Python magic methods (dunder methods)? Name at least 3 with their purposes.
2. What is Django's `signals` framework? Explain `pre_save` and `post_save` signals.
3. What is a subquery in SQL? Give a simple example.
4. What are decorators in Python? How do you write a decorator that takes arguments?
5. What is the difference between `Serializer` and `ModelSerializer` in DRF?
6. What is the `collections` module? Explain `defaultdict`, `Counter`, and `OrderedDict`.
7. What is the difference between `EXISTS` and `IN` in SQL?
8. What is Django's `STATIC_URL`? How do you serve static files?
9. What are Python's string formatting methods? Compare `%`, `.format()`, and f-strings.
10. What is the difference between composition and inheritance in OOP?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function returns a list of (index, value) pairs?
2. What SQL function rounds a number to specified decimal places?
3. What DRF field is used for write-only password fields?
4. What Python method checks if all characters in a string are digits?
5. What HTTP status code means "Bad Request"?
6. What built-in function applies a function to every item in an iterable?
7. What SQL keyword creates a temporary result set that can be referenced?
8. What Django method aggregates values across a queryset?
9. What Python keyword defines a function that returns a generator?
10. What does `JWT` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of email addresses and validates them. Return valid and invalid emails separately.
```
Input:  ["ravi@gmail.com", "invalid@", "priya@yahoo.co.in", "@no.com", "test@mail.com"]
Output: {
    "valid": ["ravi@gmail.com", "priya@yahoo.co.in", "test@mail.com"],
    "invalid": ["invalid@", "@no.com"]
}
```

**Problem 2:** Write a function that takes two sorted lists and finds the median of the combined sorted list.
```
Input:  [1, 3, 5], [2, 4, 6]
Output: 3.5
```

**Problem 3:** Write a function that compresses a string by counting consecutive repeated characters.
```
Input:  "aaabbbccddddee"
Output: "a3b3c2d4e2"

Input:  "abcde"
Output: "abcde" (no compression if result is longer)
```

**Problem 4:** Write a function that takes a CSV-formatted string and extracts specific columns.
```
csv_data = "name,age,city\nRavi,25,Chennai\nPriya,22,Mumbai\nKaran,25,Chennai"
Input:  extract_column(csv_data, "name")
Output: ["Ravi", "Priya", "Karan"]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary | manager_id | phone      |
|--------|--------|------------|--------|------------|------------|
| 1      | CEO    | Exec       | 200000 | NULL       | 9000000001 |
| 2      | Ravi   | IT         | 80000  | 1          | NULL       |
| 3      | Priya  | IT         | 55000  | 2          | 9000000003 |
| 4      | Karan  | HR         | 60000  | 1          | NULL       |
| 5      | Meena  | HR         | 65000  | 4          | 9000000005 |

**Table: sales**
| sale_id | emp_id | amount | sale_date  |
|---------|--------|--------|------------|
| 1       | 2      | 15000  | 2024-01-10 |
| 2       | 2      | 20000  | 2024-01-15 |
| 3       | 3      | 12000  | 2024-01-20 |
| 4       | 2      | 18000  | 2024-02-05 |
| 5       | 3      | 25000  | 2024-02-10 |

**Problem 1:** Write a SQL query to find employees who earn more than their manager (self-join on `employees` table with `manager_id` column).

**Problem 2:** Write a SQL query using `COALESCE` to replace NULL phone numbers with 'N/A' in the results.

**Problem 3:** Write a SQL query to find the total sales amount per employee, showing their name and total.

### Part D — OOP Based Problem

Design a quiz system:
- `Question` class with `text`, `options` (list of 4), `correct_answer` (index 0-3)
- `Quiz` class with:
  - `add_question(question)`, `start()`, `submit_answer(question_index, answer)`, `get_score()`, `get_results()`
- `get_results()` returns for each question: the question text, user's answer, correct answer, and whether it was right
- Create a quiz with 5 questions, simulate answering all, and show results

### Part E — Django Based Problem

Build a DRF API for a Contact Book:
- Model: `Contact` with fields: `name`, `phone`, `email`, `company`, `group` (choices: family, friends, work, other), `is_favorite` (BooleanField), `notes` (TextField nullable), `created_at`
- Full CRUD via ViewSet
- Custom action: `POST /contacts/{id}/favorite/` to toggle favorite status
- Filter by group, is_favorite
- Search by name, phone, company
- Ordering by name, created_at

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x for x in [True, False, True, False] if x]
print(result)
```
a) `[True, False, True, False]`
b) `[True, True]`
c) `[False, False]`
d) `[1, 0, 1, 0]`

**Q2 (MCQ):** What is the output?
```python
chars = ["a", "1", "b", "2", "c"]
result = [c for c in chars if c.isdigit()]
print(result)
```
a) `["a", "b", "c"]`
b) `["1", "2"]`
c) `[1, 2]`
d) `["a1", "b2"]`

**Q3 (MCQ):** What is the output?
```python
nums = [2, 4, 6, 8]
result = [x for x in nums if x > 3 and x < 7]
print(result)
```
a) `[2, 4, 6, 8]`
b) `[4, 6]`
c) `[4]`
d) `[6]`

**Q4 (Open-Ended):** What is the output?
```python
data = ["apple", "banana", "cherry"]
result = {w[0]: w for w in data}
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
result = [i for i in range(1, 21) if i % 4 == 0]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
area = lambda l, w=5: l * w
print(area(4))
print(area(4, 3))
```
a) `20` then `12`
b) `4` then `12`
c) `9` then `7`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
data = ["cat", "elephant", "dog", "bear"]
result = sorted(data, key=lambda x: (-len(x), x))
print(result[0])
```
a) `"cat"`
b) `"elephant"`
c) `"bear"`
d) `"dog"`

**Q8 (MCQ):** What is the output?
```python
prices = [100, 200, 300, 400]
discounted = list(map(lambda p: p * 0.9, prices))
print(discounted[1])
```
a) `200`
b) `180.0`
c) `20.0`
d) `"180"`

**Q9 (Open-Ended):** What is the output?
```python
greet = lambda name, greeting="Hello": f"{greeting}, {name}!"
print(greet("Ravi"))
print(greet("Priya", "Hi"))
```

**Q10 (Open-Ended):** What is the output?
```python
nums = [5, 3, 8, 1, 9, 2, 7]
top_3 = sorted(nums, key=lambda x: -x)[:3]
print(top_3)
```
