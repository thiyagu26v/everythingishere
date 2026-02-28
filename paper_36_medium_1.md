# 📝 Question Paper 36 — Medium 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is a Python closure? How does a nested function capture variables from the outer function?
2. What is Django ORM? How does it differ from writing raw SQL?
3. What are SQL aliases? How do you use them in queries?
4. What is the `zip()` function in Python? Give a practical example.
5. What is pagination in APIs? Why is it important?
6. What is the `__name__ == "__main__"` check in Python?
7. What is referential integrity in a database?
8. What is Django's `reverse()` function? Why is it preferred over hardcoding URLs?
9. What is the difference between mutable and immutable data types in Python?
10. What is the difference between `200 OK` and `201 Created` responses?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method checks if a string contains only numeric characters?
2. What SQL keyword changes a column's data type?
3. What DRF exception is raised for validation errors?
4. What Python built-in returns True only if all elements are True?
5. What HTTP header sends authentication credentials?
6. What function returns the current working directory in Python?
7. What SQL keyword specifies a unique constraint on a column?
8. What Django queryset method returns the first record?
9. What Python module is used for copying objects?
10. What does `ASGI` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a paragraph and returns the frequency of each word, sorted by frequency (highest first).
```
Input:  "the quick brown fox jumps over the lazy dog the fox"
Output: {"the": 3, "fox": 2, "quick": 1, "brown": 1, "jumps": 1, "over": 1, "lazy": 1, "dog": 1}
```

**Problem 2:** Write a function that validates a phone number. Valid formats: 10 digits, or starting with +91 followed by 10 digits, or with spaces/dashes.
```
Input:  "9876543210"       → True
Input:  "+91 98765 43210"  → True
Input:  "12345"            → False
```

**Problem 3:** Write a function that takes a matrix (2D list) and rotates it 90 degrees clockwise.
```
Input:  [[1, 2, 3],
         [4, 5, 6],
         [7, 8, 9]]
Output: [[7, 4, 1],
         [8, 5, 2],
         [9, 6, 3]]
```

**Problem 4:** Write a function that takes two datetime strings and returns the difference in days, hours, and minutes.
```
Input:  "2025-01-01 09:00", "2025-01-03 17:30"
Output: {"days": 2, "hours": 8, "minutes": 30}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: customers**
| customer_id | name   | email           |
|-------------|--------|-----------------|
| 1           | Ravi   | ravi@gmail.com  |
| 2           | Priya  | priya@yahoo.com |
| 3           | Karan  | karan@gmail.com |
| 4           | Meena  | meena@gmail.com |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 1           | 5000   | 2024-01-10 |
| 2        | 1           | 3000   | 2024-02-15 |
| 3        | 3           | 7000   | 2024-03-01 |

**Table: users**
| user_id | name   | email            |
|---------|--------|------------------|
| 1       | Ravi   | ravi@gmail.com   |
| 2       | Priya  | priya@yahoo.com  |

**Problem 1:** Write a SQL query to find all customers who have NOT placed any orders (use LEFT JOIN).

**Problem 2:** Write a SQL query to find the day of the week with the most orders.

**Problem 3:** Write a SQL query to create an index on the `email` column of the `users` table.

### Part D — OOP Based Problem

Create a scoring system for a game:
- `Player` class with `name`, `score` (default 0), `level` (default 1)
- Methods: `add_points(points)`, `level_up()` (levels up every 100 points), `reset()`
- `Leaderboard` class with:
  - `add_player(player)`, `remove_player(name)`, `top_players(n)` (returns top n by score)
  - `player_rank(name)` — returns rank of a specific player
  - `display()` — shows all players sorted by score
- Create 5 players, add different points, show leaderboard and specific ranks

### Part E — Django Based Problem

Build a DRF API for a Bookmark Manager:
- Model: `Bookmark` with fields: `url` (URLField), `title` (CharField), `description` (TextField, nullable), `category` (choices: tech, news, social, education, other), `is_favorite` (BooleanField), `created_at`
- ModelSerializer and ModelViewSet with full CRUD
- Filter by category and is_favorite
- Search by title and url
- Ordering by created_at and title

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
data = {"a": 1, "b": 2, "c": 3}
result = [f"{k}={v}" for k, v in data.items()]
print(result)
```
a) `["a", "b", "c"]`
b) `["a=1", "b=2", "c=3"]`
c) `[1, 2, 3]`
d) `{"a": 1, "b": 2, "c": 3}`

**Q2 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5, 6, 7, 8]
result = [x for x in nums if x % 3 == 0]
print(result)
```
a) `[1, 2, 4, 5, 7, 8]`
b) `[3, 6]`
c) `[3, 6, 9]`
d) `[0, 3, 6]`

**Q3 (MCQ):** What is the output?
```python
words = ["Hi", "Hello", "Hey"]
result = [w for w in words if len(w) > 2]
print(result)
```
a) `["Hi"]`
b) `["Hello", "Hey"]`
c) `["Hi", "Hello", "Hey"]`
d) `[5, 3]`

**Q4 (Open-Ended):** What is the output?
```python
matrix = [[1, 2], [3, 4], [5, 6]]
result = [row[1] for row in matrix]
print(result)
```

**Q5 (Open-Ended):** What is the output?
```python
nums = list(range(1, 6))
result = [sum(nums[:i+1]) for i in range(len(nums))]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
repeat = lambda s, n: s * n
print(repeat("ha", 3))
```
a) `"ha3"`
b) `"hahaha"`
c) `"ha ha ha"`
d) `["ha", "ha", "ha"]`

**Q7 (MCQ):** What is the output?
```python
data = [("apples", 5), ("bananas", 2), ("oranges", 8)]
result = sorted(data, key=lambda x: x[1])
print(result[0][0])
```
a) `"apples"`
b) `"bananas"`
c) `"oranges"`
d) `2`

**Q8 (MCQ):** What is the output?
```python
nums = [15, 22, 33, 44, 55]
result = list(filter(lambda x: x % 11 == 0, nums))
print(result)
```
a) `[15]`
b) `[22, 33, 44, 55]`
c) `[11, 22, 33, 44, 55]`
d) `[]`

**Q9 (Open-Ended):** What is the output?
```python
make_adder = lambda n: lambda x: x + n
add_5 = make_adder(5)
print(add_5(10))
```

**Q10 (Open-Ended):** What is the output?
```python
data = [1, 2, 3, 4, 5]
result = list(map(lambda x: "even" if x % 2 == 0 else "odd", data))
print(result)
```
