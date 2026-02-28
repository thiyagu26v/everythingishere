# 📝 Question Paper 38 — Medium 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is a Python iterator? How is it different from an iterable?
2. What is Django's `context` in views? How do you pass data to templates?
3. What is a self-join in SQL? When would you use it?
4. What are Python's `any()` and `all()` functions? Give examples.
5. What is content type in HTTP? What does `application/json` mean?
6. What is the `try-except-else-finally` block in Python? When does `else` execute?
7. What is the difference between `CHAR(10)` and `VARCHAR(10)` in SQL?
8. What is Django's `choices` field option? How does it work?
9. What is the `enumerate()` function? Why is it better than a manual counter?
10. What is HTTPS? How is it different from HTTP?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method removes and returns an item by index from a list?
2. What SQL keyword defines a column's default value?
3. What DRF renderer converts data to JSON format?
4. What Python function checks if a string can be converted to a number?
5. What HTTP status code means "Gateway Timeout"?
6. What built-in function sorts a dictionary by its keys?
7. What SQL keyword temporarily renames a table in a query?
8. What Django tag loads custom template tags?
9. What Python method finds the position of a substring in a string?
10. What does `TCP` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of dates (as strings) and returns the dates sorted in chronological order.
```
Input:  ["2025-03-15", "2025-01-01", "2025-02-28", "2024-12-31"]
Output: ["2024-12-31", "2025-01-01", "2025-02-28", "2025-03-15"]
```

**Problem 2:** Write a function that takes a paragraph and returns the sentence with the most words.
```
Input:  "I love Python. Python is a great programming language. It is easy."
Output: "Python is a great programming language."
```

**Problem 3:** Write a class `Stack` with methods `push(item)`, `pop()`, `peek()`, `is_empty()`, `size()`, and `display()`. Implement using a Python list.
```
s = Stack()
s.push(10)
s.push(20)
s.push(30)
s.peek()    → 30
s.pop()     → 30
s.size()    → 2
```

**Problem 4:** Write a function that takes a list of employee dicts and returns employees grouped by salary brackets: "low" (< 30000), "mid" (30000-60000), "high" (> 60000).
```
Input:  [{"name": "Ravi", "salary": 25000}, {"name": "Priya", "salary": 55000}, {"name": "Karan", "salary": 80000}]
Output: {"low": ["Ravi"], "mid": ["Priya"], "high": ["Karan"]}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 101         | 5000   | 2024-01-10 |
| 2        | 102         | 3000   | 2024-03-15 |
| 3        | 101         | 7000   | 2024-05-01 |
| 4        | 103         | 2000   | 2024-07-20 |
| 5        | 102         | 4000   | 2024-09-10 |

**Table: users**
| user_id | first_name | last_name |
|---------|------------|-----------|
| 1       | Ravi       | Kumar     |
| 2       | Priya      | Sharma    |
| 3       | Karan      | Singh     |

**Table: products**
| product_id | name     | price | category    |
|------------|----------|-------|-------------|
| 1          | Laptop   | 50000 | Electronics |
| 2          | Mouse    | 500   | Electronics |
| 3          | Monitor  | 20000 | Electronics |
| 4          | Pen      | 20    | Stationery  |

**Problem 1:** Write a SQL query to find the number of orders placed each month in 2024.

**Problem 2:** Write a SQL query to swap the values of two columns (`first_name` and `last_name`) in the `users` table.

**Problem 3:** Write a SQL query to find products that are more expensive than the average product in their category.

### Part D — OOP Based Problem

Design a simple notification system:
- `Notification` class with `notification_id`, `title`, `message`, `type` (info/warning/error), `is_read` (default False), `created_at`
- `NotificationCenter` class with:
  - `send(title, message, type)` — creates a notification
  - `read(notification_id)` — marks as read
  - `unread_notifications()` — returns all unread
  - `filter_by_type(type)` — returns notifications of a specific type
  - `mark_all_read()` — marks all as read
  - `delete_read()` — removes all read notifications
  - `summary()` — total, unread count, count by type
- Create 8 notifications of different types, read some, show summary

### Part E — Django Based Problem

Build a DRF API for a Recipe app:
- Model: `Recipe` with fields: `name`, `ingredients` (TextField), `instructions` (TextField), `prep_time` (IntegerField, minutes), `cuisine` (CharField), `difficulty` (choices: easy/medium/hard), `servings` (IntegerField), `created_at`
- ModelSerializer and ModelViewSet
- Filter by cuisine, difficulty
- Search on name and ingredients
- Custom action: `GET /recipes/quick/` — returns recipes with prep_time < 30 minutes
- Ordering by prep_time, name, created_at
