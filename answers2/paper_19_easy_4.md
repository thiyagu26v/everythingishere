# 📝 Question Paper 19 — Easy 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is a for loop vs a while loop? When would you use each?
2. What are static files in Django? Give examples.
3. What is the `AUTO_INCREMENT` (or `SERIAL`) keyword in SQL?
4. What is the difference between a local variable and a global variable in Python?
5. What is a serializer in DRF? Why do we need it?
6. What is `NULL` in SQL? How is it different from 0 or empty string?
7. What is encapsulation in OOP? Give a simple example.
8. What is the difference between `GET` and `POST` requests with examples?
9. What are f-strings in Python? How are they used?
10. What is the purpose of `__pycache__` folder in Python?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function returns the absolute value of a number?
2. What SQL keyword is used to combine two conditions?
3. What Django tag loads static files in templates?
4. What Python method checks if a string starts with a specific prefix?
5. What HTTP status code means "Redirect"?
6. What function converts a Python object to a JSON string?
7. What SQL keyword specifies a column cannot have NULL values?
8. What Python keyword defines a function?
9. What Django field is used for storing email addresses?
10. What does `URL` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of numbers and returns a dictionary with counts of positive, negative, and zero values.
```
Input:  [1, -2, 0, 3, -5, 0, 7]
Output: {"positive": 3, "negative": 2, "zero": 2}
```

**Problem 2:** Write a function that converts a list of words into title case (first letter uppercase, rest lowercase).
```
Input:  ["hello", "WORLD", "pYtHoN"]
Output: ["Hello", "World", "Python"]
```

**Problem 3:** Write a function that takes a dictionary and swaps its keys and values.
```
Input:  {"a": 1, "b": 2, "c": 3}
Output: {1: "a", 2: "b", 3: "c"}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: customers**
| customer_id | name   | email           | phone      |
|-------------|--------|-----------------|------------|
| 1           | Ravi   | ravi@gmail.com  | 9876543210 |
| 2           | Priya  | priya@yahoo.com | 8765432109 |

**Table: products**
| product_id | name       | price | category    |
|------------|------------|-------|-------------|
| 1          | iPhone Pro | 80000 | Electronics |
| 2          | Pen Pro    | 150   | Stationery  |
| 3          | Laptop Pro | 65000 | Electronics |

**Table: order_items**
| item_id | order_id | product_id | price  | quantity |
|---------|----------|------------|--------|----------|
| 1       | 1        | 1          | 80000  | 1        |
| 2       | 1        | 2          | 150    | 3        |
| 3       | 2        | 3          | 65000  | 2        |

**Problem 1:** Write a SQL query to add a new column `phone` (VARCHAR) to the `customers` table.

**Problem 2:** Write a SQL query to find all products whose name contains the word "Pro".

**Problem 3:** Write a SQL query to calculate the total revenue (price × quantity) from the `order_items` table.

### Part D — OOP Based Problem

Create a class `Playlist` with:
- Attributes: `name`, `songs` (list)
- Methods: `add_song(song_name)`, `remove_song(song_name)`, `shuffle()` (randomize order), `show_songs()`, `total_songs()`
- The `remove_song` method should handle the case when the song doesn't exist
- Create a playlist, add 5 songs, shuffle, show the shuffled list

### Part E — Django Based Problem

Create a Django model `Employee` with fields: `name`, `email`, `department`, `salary`, `date_joined`. Write a DRF serializer and create two views: one to list all employees and one to get a single employee by ID. Use `APIView` class.

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [min(x, 10) for x in [5, 12, 8, 15, 3]]
print(result)
```
a) `[5, 12, 8, 15, 3]`
b) `[5, 10, 8, 10, 3]`
c) `[10, 10, 10, 10, 10]`
d) `[5, 8, 3]`

**Q2 (MCQ):** What is the output?
```python
result = [i for i in "hello world" if i.isalpha()]
print(len(result))
```
a) `11`
b) `10`
c) `5`
d) `2`

**Q3 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = [n for n in nums if n != 3]
print(result)
```
a) `[3]`
b) `[1, 2, 4, 5]`
c) `[1, 2, 3, 4, 5]`
d) `[]`

**Q4 (Open-Ended):** What is the output?
```python
result = [x * y for x, y in [(2, 3), (4, 5), (6, 7)]]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
words = ["hi", "hello", "hey"]
result = [w + " there" for w in words]
print(result[1])
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
first_char = lambda s: s[0]
print(first_char("Python"))
```
a) `"Python"`
b) `"P"`
c) `"p"`
d) `0`

**Q7 (MCQ):** What is the output?
```python
result = list(map(lambda x: x.count("l"), ["hello", "world", "lily"]))
print(result)
```
a) `["l", "l", "ll"]`
b) `[2, 1, 2]`
c) `[1, 1, 1]`
d) `3`

**Q8 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
result = list(filter(lambda x: x % 3 == 0, nums))
print(result)
```
a) `[1, 2, 4, 5, 7, 8, 10]`
b) `[3, 6, 9]`
c) `[0, 0, 0]`
d) `[3, 9]`

**Q9 (Open-Ended):** What is the output?
```python
concat = lambda *args: " ".join(args)
print(concat("I", "love", "Python"))
```

**Q10 (Open-Ended):** What is the output?
```python
data = [("Ravi", 80), ("Priya", 95), ("Karan", 60)]
result = min(data, key=lambda x: x[1])
print(result)
```
