# 📝 Question Paper 39 — Medium 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the `__init__` method in Python? Why is it called a constructor?
2. What is Django's `annotate()` method? Give an example with `Count`.
3. What is a subquery in SQL? How is it different from a JOIN?
4. What are Python's `@staticmethod` and `@classmethod`? When do you use each?
5. What is the difference between `APIView` and `ViewSet` in DRF?
6. What is `pdb` in Python? How do you use it for debugging?
7. What is a foreign key constraint? What happens if you delete a referenced row?
8. How does Django's template inheritance work? Explain `{% block %}` and `{% extends %}`.
9. What are Python's `__eq__`, `__lt__`, and `__gt__` methods? What do they do?
10. What is database seeding? Why is it useful in development?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function unpacks dictionary keys into a list?
2. What SQL function concatenates two strings?
3. What DRF mixin provides list functionality?
4. What Python operator checks if two variables reference the same object?
5. What HTTP status code means "Request Timeout"?
6. What built-in function creates a set from an iterable?
7. What SQL command grants permissions to a user?
8. What Django field choice option stores human-readable labels?
9. What Python keyword creates a loop that runs while a condition is True?
10. What does `SMTP` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a dictionary of items and prices, and a budget amount. Return the maximum number of items that can be bought within the budget (buy cheapest first).
```
Input:  items = {"pen": 10, "book": 50, "bag": 200, "eraser": 5, "pencil": 8}, budget = 75
Output: {"items_bought": ["eraser", "pencil", "pen", "book"], "total_spent": 73, "remaining": 2}
```

**Problem 2:** Write a function that checks if two strings are rotations of each other.
```
Input:  "abcde", "cdeab"
Output: True

Input:  "abcde", "abced"
Output: False
```

**Problem 3:** Write a function that takes a list of integers and finds all pairs that sum to a given target.
```
Input:  [1, 5, 7, -1, 5], target = 6
Output: [(1, 5), (7, -1)]  (no duplicate pairs)
```

**Problem 4:** Write a function that reads a multi-line string of key=value pairs and converts it to a dictionary.
```
Input:  "name=Ravi\nage=25\ncity=Chennai\nis_active=true"
Output: {"name": "Ravi", "age": "25", "city": "Chennai", "is_active": "true"}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: customers**
| customer_id | name   |
|-------------|--------|
| 1           | Ravi   |
| 2           | Priya  |
| 3           | Karan  |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 1           | 15000  | 2024-01-10 |
| 2        | 1           | 20000  | 2024-02-15 |
| 3        | 2           | 8000   | 2024-01-20 |
| 4        | 3           | 12000  | 2024-03-01 |
| 5        | 2           | 5000   | 2024-04-10 |

**Table: enrollments**
| enrollment_id | student_id | course_id |
|---------------|------------|-----------|
| 1             | 1          | 101       |
| 2             | 1          | 102       |
| 3             | 2          | 101       |

**Table: employees**
| emp_id | name   | department | hire_date  |
|--------|--------|------------|------------|
| 1      | Ravi   | IT         | 2023-06-15 |
| 2      | Priya  | HR         | 2024-01-20 |
| 3      | Karan  | IT         | 2023-06-15 |
| 4      | Meena  | Sales      | 2024-03-10 |

**Problem 1:** Write a SQL query to find the top 5 customers by total purchase amount.

**Problem 2:** Write a SQL query to add a composite unique constraint on `student_id` and `course_id` in the `enrollments` table.

**Problem 3:** Write a SQL query to find all employees who joined in the same year as employee 'Ravi'.

### Part D — OOP Based Problem

Design a simple chat system:
- `Message` class with `sender`, `text`, `timestamp`
- `ChatRoom` class with:
  - `name`, `members` (list of names), `messages` (list)
  - `add_member(name)`, `remove_member(name)`
  - `send_message(sender, text)` — only members can send
  - `get_messages(last_n=None)` — returns last N messages or all
  - `search_messages(keyword)` — returns messages containing keyword
  - `member_count()`, `message_count()`
- Create a chat room, add 4 members, send 8 messages, search for a keyword, show last 3 messages

### Part E — Django Based Problem

Build a DRF API for a Coupon System:
- Model: `Coupon` with fields: `code` (unique CharField), `discount_percent` (IntegerField), `min_order_value` (DecimalField), `max_uses` (IntegerField), `times_used` (IntegerField default 0), `is_active` (BooleanField), `expires_at` (DateTimeField)
- ViewSet with full CRUD
- Custom action: `POST /coupons/validate/` — accepts `code` and `order_value`, returns whether the coupon is valid (active, not expired, not maxed out, meets minimum order) and the discount amount
- Filter by is_active
- List only active and non-expired coupons
