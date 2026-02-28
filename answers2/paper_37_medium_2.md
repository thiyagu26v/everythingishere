# 📝 Question Paper 37 — Medium 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `args` and `kwargs` in Python? When do you use them?
2. What is Django's `get_or_create()` method? Give a use case.
3. What is the difference between `IN` and `EXISTS` in SQL?
4. What is a class method vs an instance method in Python?
5. What are DRF serializer validators? How do you add custom validation?
6. What is the `os` module in Python? Name 5 useful functions.
7. What are SQL constraints? Explain `CHECK` and `DEFAULT`.
8. What is the purpose of `__init__.py` in Django apps?
9. What is a race condition? Give a simple example.
10. What is the difference between `filter()` and `get()` in Django ORM?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function creates a boolean mask from a condition?
2. What SQL command shows the structure of a table?
3. What DRF class handles multiple serialization of nested objects?
4. What Python method returns the index of an element in a list?
5. What HTTP status code means "Unprocessable Entity"?
6. What built-in function creates a dictionary from two lists?
7. What SQL constraint ensures values in a column are unique across rows?
8. What Django shortcut renders a template with context data?
9. What Python term describes a function that calls itself?
10. What does `MVC` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of timestamps and returns the busiest hour (hour with most entries).
```
Input:  ["09:15", "09:30", "10:00", "09:45", "14:00", "14:30", "10:15"]
Output: 9  (3 entries in hour 9)
```

**Problem 2:** Write a function that converts a nested dictionary to a flat dictionary with path-like keys using `/` separator.
```
Input:  {"user": {"name": "Ravi", "address": {"city": "Chennai", "pin": "600001"}}}
Output: {"user/name": "Ravi", "user/address/city": "Chennai", "user/address/pin": "600001"}
```

**Problem 3:** Write a function that implements a simple text search. Given a list of documents (strings), return documents containing all search keywords.
```
Input:  docs = ["Python is great for web", "Django uses Python", "Java is popular"], keywords = ["Python", "great"]
Output: ["Python is great for web"]
```

**Problem 4:** Write a function that takes a list of interval tuples and checks if any person has double-booked (overlapping events).
```
Input:  [("09:00", "10:00"), ("10:00", "11:30"), ("11:00", "12:00")]
Output: True  (10:00-11:30 and 11:00-12:00 overlap)
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: products**
| product_id | name     | price | category    |
|------------|----------|-------|-------------|
| 1          | Laptop   | 50000 | Electronics |
| 2          | Mouse    | 350   | Electronics |
| 3          | Notebook | 100   | Stationery  |
| 4          | Headset  | 2500  | Electronics |
| 5          | Pen      | 20    | Stationery  |

**Table: order_items**
| item_id | order_id | product_id | quantity | price |
|---------|----------|------------|----------|-------|
| 1       | 1        | 1          | 2        | 50000 |
| 2       | 2        | 2          | 5        | 350   |
| 3       | 3        | 4          | 1        | 2500  |
| 4       | 4        | 1          | 1        | 50000 |

**Table: students**
| student_id | name   |
|------------|--------|
| 1          | Ravi   |
| 2          | Priya  |

**Table: enrollments**
| enrollment_id | student_id | course_id |
|---------------|------------|-----------|
| 1             | 1          | 101       |
| 2             | 1          | 102       |
| 3             | 2          | 101       |

**Table: courses**
| course_id | name      |
|-----------|-----------|
| 101       | Python    |
| 102       | Django    |
| 103       | SQL       |

**Problem 1:** Write a SQL query using `CASE WHEN` to categorize products: 'Budget' (price < 500), 'Standard' (500-2000), 'Premium' (> 2000).

**Problem 2:** Write a SQL query to find the top 3 categories by total revenue.

**Problem 3:** Write a SQL query to join three tables: `students`, `enrollments`, `courses` to show each student's enrolled courses.

### Part D — OOP Based Problem

Design a movie rental system:
- `Movie` class with `title`, `genre`, `year`, `copies_available`, `rental_price`
- `Customer` class with `name`, `customer_id`, `rented_movies` (list), `rental_history`
- `RentalStore` class with:
  - `add_movie(movie)`, `rent_movie(customer_id, movie_title)`, `return_movie(customer_id, movie_title)`
  - `search_movies(keyword)` — search by title or genre
  - `customer_bill(customer_id)` — total rental charges
  - `popular_movies()` — most rented movies
- Handle: renting unavailable movie, returning unrented movie
- Demonstrate with 5 movies and 3 customers

### Part E — Django Based Problem

Build a DRF API for an Announcement Board:
- Model: `Announcement` with fields: `title`, `body`, `author_name`, `priority` (choices: low/medium/high), `is_active` (BooleanField), `expires_at` (DateTimeField nullable), `created_at`
- ViewSet with full CRUD
- Only show active and non-expired announcements in listing
- Custom action: `POST /announcements/{id}/deactivate/` to set is_active to False
- Filter by priority, author_name
- Ordering by priority, created_at

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
s = "Hello World"
result = [c for c in s if c != " "]
print("".join(result))
```
a) `"Hello World"`
b) `"HelloWorld"`
c) `"Hello"`
d) `"helloworld"`

**Q2 (MCQ):** What is the output?
```python
nums = [1, -2, 3, -4, 5]
result = [abs(x) for x in nums]
print(result)
```
a) `[1, -2, 3, -4, 5]`
b) `[1, 2, 3, 4, 5]`
c) `[-1, 2, -3, 4, -5]`
d) `[0, 0, 0, 0, 0]`

**Q3 (MCQ):** What is the output?
```python
names = ["Alice", "Bob", "Charlie"]
result = {name: len(name) for name in names}
print(result["Bob"])
```
a) `"Bob"`
b) `3`
c) `1`
d) `["B", "o", "b"]`

**Q4 (Open-Ended):** What is the output?
```python
nums = [10, 20, 30, 40]
result = [nums[i] - nums[i-1] for i in range(1, len(nums))]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
text = "abcde"
result = [text[i:] for i in range(len(text))]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
check = lambda x: "positive" if x > 0 else "zero" if x == 0 else "negative"
print(check(0))
```
a) `"positive"`
b) `"zero"`
c) `"negative"`
d) `0`

**Q7 (MCQ):** What is the output?
```python
colors = ["red", "green", "blue", "yellow"]
result = sorted(colors, key=lambda c: c[-1])
print(result[0])
```
a) `"red"`
b) `"blue"`
c) `"green"`
d) `"yellow"`

**Q8 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
result = list(filter(lambda x: x % 2 == 0 and x > 5, nums))
print(result)
```
a) `[2, 4, 6, 8, 10]`
b) `[6, 8, 10]`
c) `[6, 7, 8, 9, 10]`
d) `[1, 3, 5, 7, 9]`

**Q9 (Open-Ended):** What is the output?
```python
compose = lambda f, g: lambda x: f(g(x))
double = lambda x: x * 2
increment = lambda x: x + 1
print(compose(double, increment)(5))
```

**Q10 (Open-Ended):** What is the output?
```python
records = [{"name": "A", "score": 50}, {"name": "B", "score": 90}, {"name": "C", "score": 70}]
passing = list(filter(lambda r: r["score"] >= 60, records))
print([r["name"] for r in passing])
```
