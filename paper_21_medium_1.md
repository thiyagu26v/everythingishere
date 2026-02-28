# 📝 Question Paper 21 — Medium 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `==` and `is` in Python? Explain with mutable objects.
2. Explain how Django middleware works. Give an example of built-in middleware.
3. What is the difference between `UNION` and `UNION ALL` in SQL?
4. What is a Python generator? How is it different from a regular function?
5. What is token-based authentication in DRF? How does it work?
6. What is the `with` statement in Python? Why is it used with files?
7. What are SQL subqueries? Give a simple example.
8. What is the difference between `CharField` and `TextField` in Django models?
9. What is a virtual environment? Why should every project have one?
10. What is polymorphism in Python? Give a simple example.

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method returns all keys of a dictionary?
2. What SQL function converts a value to uppercase?
3. What DRF decorator is used to create a simple function-based API view?
4. What Python keyword creates a generator function?
5. What HTTP header specifies the format of the request body?
6. What built-in function checks if any element in a list is True?
7. What SQL keyword is used to give a column an alias name?
8. What Django method filters querysets and returns matching objects?
9. What Python module is used for regular expressions?
10. What does `ORM` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of dictionaries with `product` and `price`, and returns the products grouped by price range: "cheap" (< 100), "medium" (100-500), "expensive" (> 500).
```
Input:  [{"product": "Pen", "price": 20}, {"product": "Bag", "price": 300}, {"product": "Laptop", "price": 60000}, {"product": "Book", "price": 150}]
Output: {"cheap": ["Pen"], "medium": ["Bag", "Book"], "expensive": ["Laptop"]}
```

**Problem 2:** Write a function that takes a list of numbers and returns a new list where each number is replaced by its rank (position when sorted, starting from 1).
```
Input:  [40, 10, 30, 20]
Output: [4, 1, 3, 2]
```

**Problem 3:** Write a function that takes a list of strings and returns the strings sorted by their length (shortest first). If two strings have the same length, maintain their original order.
```
Input:  ["banana", "cat", "apple", "hi", "dog"]
Output: ["hi", "cat", "dog", "apple", "banana"]
```

**Problem 4:** Write a function that merges two dictionaries. If a key exists in both, the values should be combined into a list.
```
Input:  {"a": 1, "b": 2}, {"b": 3, "c": 4}
Output: {"a": 1, "b": [2, 3], "c": 4}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 65000  |
| 2      | Priya  | HR         | 45000  |
| 3      | Karan  | IT         | 72000  |
| 4      | Meena  | Sales      | 38000  |
| 5      | Arjun  | HR         | 52000  |

**Table: customers**
| customer_id | name   |
|-------------|--------|
| 1           | Ravi   |
| 2           | Priya  |
| 3           | Karan  |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 1           | 5000   | 2024-01-10 |
| 2        | 1           | 3000   | 2024-02-15 |
| 3        | 2           | 7000   | 2024-01-20 |
| 4        | 1           | 2000   | 2024-03-05 |
| 5        | 3           | 4500   | 2024-02-28 |

**Problem 1:** Write a SQL query to find the second highest salary from the `employees` table using a subquery.

**Problem 2:** Write a SQL query to join `orders` and `customers` tables and show each customer's name along with their total order amount.

**Problem 3:** Write a SQL query to find departments where the average salary is above 50000.

### Part D — OOP Based Problem

Create a class `Inventory` with:
- Attributes: `items` (dict mapping item name to dict with `quantity` and `price`)
- Methods: `add_item(name, qty, price)`, `sell_item(name, qty)`, `restock(name, qty)`, `get_value()`, `low_stock_items(threshold)`
- `sell_item` should reduce quantity and raise error if not enough stock
- `get_value()` returns total value of all inventory
- `low_stock_items(5)` returns names of items with quantity below 5
- Demonstrate with at least 4 items

### Part E — Django Based Problem

Build a DRF API for a `Student` model:
- Fields: `name`, `roll_number` (unique), `department`, `semester` (IntegerField), `cgpa` (FloatField), `is_active` (BooleanField)
- Create model, serializer, viewset, and URL config
- Add filtering by `department` and `semester`
- Add search on `name`
- Add ordering by `cgpa` and `name`

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x.replace("a", "@") for x in ["apple", "banana", "cat"]]
print(result)
```
a) `["apple", "banana", "cat"]`
b) `["@pple", "b@n@n@", "c@t"]`
c) `["pple", "bnn", "ct"]`
d) `["@", "@@@", "@"]`

**Q2 (MCQ):** What is the output?
```python
nums = list(range(10))
result = [nums[i] for i in range(0, len(nums), 3)]
print(result)
```
a) `[0, 1, 2, 3]`
b) `[0, 3, 6, 9]`
c) `[3, 6, 9]`
d) `[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]`

**Q3 (MCQ):** What is the output?
```python
pairs = [(1, "a"), (2, "b"), (3, "c")]
result = [f"{n}-{c}" for n, c in pairs]
print(result)
```
a) `[(1, "a"), (2, "b"), (3, "c")]`
b) `["1-a", "2-b", "3-c"]`
c) `["1a", "2b", "3c"]`
d) `["a-1", "b-2", "c-3"]`

**Q4 (Open-Ended):** What is the output?
```python
text = "Hello World"
result = {c.lower() for c in text if c.isalpha()}
print(sorted(result))
```

**Q5 (Open-Ended):** What is the output?
```python
nums = [3, 1, 4, 1, 5, 9]
result = [(i, x) for i, x in enumerate(nums) if x > 3]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
grade = lambda score: "A" if score >= 90 else "B" if score >= 80 else "C" if score >= 70 else "F"
print(grade(85))
```
a) `"A"`
b) `"B"`
c) `"C"`
d) `"F"`

**Q7 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = list(map(lambda x: x ** 2 if x % 2 != 0 else x, nums))
print(result)
```
a) `[1, 4, 9, 16, 25]`
b) `[1, 2, 9, 4, 25]`
c) `[2, 4, 6, 8, 10]`
d) `[1, 2, 3, 4, 5]`

**Q8 (MCQ):** What is the output?
```python
words = ["Python", "Java", "C", "JavaScript", "Go"]
result = sorted(words, key=lambda w: len(w))
print(result[0])
```
a) `"Python"`
b) `"C"`
c) `"Go"`
d) `"JavaScript"`

**Q9 (Open-Ended):** What is the output?
```python
make_multiplier = lambda n: lambda x: x * n
triple = make_multiplier(3)
print(triple(7))
```

**Q10 (Open-Ended):** What is the output?
```python
data = [{"item": "pen", "price": 10}, {"item": "book", "price": 50}, {"item": "bag", "price": 200}]
total = sum(map(lambda x: x["price"], data))
print(total)
```
