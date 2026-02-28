# 📝 Question Paper 08 — Medium 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between an iterable and an iterator in Python?
2. What are Django model managers? When would you write a custom manager?
3. What are subqueries in SQL? Give a simple example.
4. Explain how Python handles memory management and garbage collection.
5. What are DRF throttling and rate limiting? Why are they important?
6. What is the difference between `process_request` and `process_response` in Django middleware?
7. What is the difference between a subquery and a JOIN in SQL?
8. What is a Python class? How do you create a simple class with attributes and methods?
9. What is CORS? How do you handle it in Django?
10. Explain the concept of "fat models, thin views" in Django.

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python module provides tools for creating iterators?
2. What SQL keyword is used to rename a column or table in a query?
3. What DRF feature controls who can access a particular API endpoint?
4. What Python data type is immutable and hashable like a tuple but has set operations?
5. What Django method is used to get a single object or raise a 404 error?
6. What HTTP method is used to partially update a resource?
7. What SQL constraint ensures referential integrity?
8. What Python built-in function creates a dictionary from key-value pairs?
9. What Django package is commonly used for user token authentication?
10. What design principle does the Single Responsibility Principle belong to?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that merges two sorted lists into a single sorted list without using the built-in `sort()` or `sorted()`.
```
Input:  [1, 3, 5, 7], [2, 4, 6, 8]
Output: [1, 2, 3, 4, 5, 6, 7, 8]
```

**Problem 2:** Write a class `Stack` that implements push, pop, peek, is_empty, and size methods using a Python list internally.
```
s = Stack()
s.push(10)
s.push(20)
s.push(30)
s.peek()      → 30
s.pop()       → 30
s.size()      → 2
s.is_empty()  → False
```

**Problem 3:** Implement a function that performs matrix multiplication on two 2D lists. Validate that the dimensions are compatible.
```
Input:  A = [[1, 2], [3, 4]], B = [[5, 6], [7, 8]]
Output: [[19, 22], [43, 50]]
```

**Problem 4:** Write a function that finds all pairs of numbers in a list that sum to a given target value.
```
Input:  nums = [2, 4, 3, 5, 7, 8, 1], target = 9
Output: [(2, 7), (4, 5), (8, 1)]
```

### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name    | department | salary |
|--------|---------|------------|--------|
| 1      | Ravi    | IT         | 25000  |
| 2      | Priya   | HR         | 35000  |
| 3      | Karan   | IT         | 55000  |
| 4      | Meena   | Sales      | 42000  |
| 5      | Arjun   | HR         | 65000  |
| 6      | Divya   | Sales      | 28000  |
| 7      | Suresh  | IT         | 78000  |

**Problem 1:** Write a SQL query to find departments where the total salary is more than 60000.

**Problem 2:** Write a SQL query using `CASE WHEN` to categorize employees into salary bands: 'Low' (< 30000), 'Medium' (30000-60000), 'High' (> 60000).

**Problem 3:** Write a SQL query to find the nth highest salary using `LIMIT` and `OFFSET`.

### Part D — OOP Based Problem

Design an e-commerce cart system:
- `Product` class with `name`, `price`, `stock_quantity`
- `CartItem` class with `product`, `quantity`
- `ShoppingCart` class with methods:
  - `add_item(product, quantity)` — check stock availability
  - `remove_item(product_name)`
  - `update_quantity(product_name, new_quantity)`
  - `calculate_total()`
  - `checkout()` — reduce stock and clear cart
- Handle edge cases: adding more than available stock, removing non-existent items

### Part E — Django Based Problem

Build a simple Todo API with DRF:
- Model: `Todo` with fields: `title`, `description`, `priority` (choices: low, medium, high), `is_completed`, `due_date`, `created_at`
- Add filtering by `priority` and `is_completed`
- Add ordering by `due_date` and `created_at`
- Add search functionality on `title` and `description`
- Use `ModelViewSet` with a router

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [[j for j in range(i)] for i in range(1, 4)]
print(result)
```
a) `[[0], [0, 1], [0, 1, 2]]`
b) `[[1], [1, 2], [1, 2, 3]]`
c) `[[0, 1, 2], [0, 1, 2], [0, 1, 2]]`
d) `[[1, 2, 3]]`

**Q2 (MCQ):** What is the output?
```python
result = [x for x in "abcdef" if x not in "ace"]
print(result)
```
a) `["a", "c", "e"]`
b) `["b", "d", "f"]`
c) `["abcdef"]`
d) `["bdf"]`

**Q3 (MCQ):** What is the output?
```python
d = {"a": 1, "b": 2, "c": 3}
result = [k * v for k, v in d.items()]
print(result)
```
a) `["a", "bb", "ccc"]`
b) `[("a", 1), ("b", 2), ("c", 3)]`
c) `["a1", "b2", "c3"]`
d) `[1, 4, 9]`

**Q4 (Open-Ended):** What is the output?
```python
result = [x for x in range(20) if x % 2 == 0 and x % 3 == 0]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
sentence = "the quick brown fox"
result = {word: len(word) for word in sentence.split()}
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
check = lambda x: "positive" if x > 0 else "negative" if x < 0 else "zero"
print(check(-5))
print(check(0))
```
a) `"negative"` then `"zero"`
b) `"positive"` then `"zero"`
c) `"negative"` then `"negative"`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
words = ["Python", "is", "amazing"]
result = list(map(lambda w: (w, len(w)), words))
print(result)
```
a) `["Python", "is", "amazing"]`
b) `[6, 2, 7]`
c) `[("Python", 6), ("is", 2), ("amazing", 7)]`
d) `[("P", 6), ("i", 2), ("a", 7)]`

**Q8 (MCQ):** What is the output?
```python
data = [("Ravi", 88), ("Priya", 95), ("Karan", 72), ("Meena", 91)]
result = sorted(data, key=lambda x: x[1], reverse=True)
print(result[0][0])
```
a) `"Ravi"`
b) `"Karan"`
c) `"Priya"`
d) `"Meena"`

**Q9 (Open-Ended):** What is the output?
```python
apply = lambda f, x: f(x)
print(apply(lambda x: x * 3, 7))
```

**Q10 (Open-Ended):** What is the output?
```python
nums = [3, 1, 4, 1, 5, 9, 2]
result = sorted(nums, key=lambda x: abs(x - 5))
print(result[:3])
```
