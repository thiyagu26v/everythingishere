# 📝 Question Paper 30 — Advanced 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `hasattr()`, `getattr()`, and `setattr()` in Python?
2. How does Django handle database migrations? What happens when you have conflicting migrations?
3. What are SQL CTEs (Common Table Expressions)? How are they different from subqueries?
4. What is the `__init__` method in Python? How does it work as a constructor?
5. What are DRF serializer relations? Explain `PrimaryKeyRelatedField` vs `SlugRelatedField` vs `StringRelatedField`.
6. What are abstract classes in Python? How are they different from regular classes?
7. What is the difference between `JOIN`, `SUBQUERY`, and `EXISTS` for performance?
8. What are Django signals? Give examples of `pre_save`, `post_save`, and `post_delete`.
9. What is the `logging` module in Python? Why is it better than `print()` for debugging?
10. What is the difference between REST and WebSocket? When would you use each?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method checks if a dictionary has a specific key?
2. What SQL clause is used to sort results in descending order?
3. What DRF module handles URL routing for ViewSets?
4. What Python function rounds a float to a given number of decimal places?
5. What HTTP status code means "Too Many Requests"?
6. What built-in function creates an iterator from a callable with a sentinel value?
7. What SQL function replaces occurrences of a substring within a string?
8. What Django ORM method performs bulk creation of objects?
9. What Python magic method makes an object iterable?
10. What does `SSL` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of student marks across multiple tests and calculates: best test score, worst test score, improvement trend (improving/declining/stable), and consistency score (standard deviation).
```
Input:  {"Ravi": [60, 65, 70, 75, 80], "Priya": [90, 85, 80, 75, 70]}
Output: {
    "Ravi": {"best": 80, "worst": 60, "trend": "improving", "consistency": 7.07},
    "Priya": {"best": 90, "worst": 70, "trend": "declining", "consistency": 7.07}
}
```

**Problem 2:** Write a function that takes a list of strings and returns a dictionary with words as keys and a list of sentences containing that word as values.
```
Input:  ["Python is great", "Java is popular", "Python is easy"]
Output: {
    "Python": ["Python is great", "Python is easy"],
    "is": ["Python is great", "Java is popular", "Python is easy"],
    "great": ["Python is great"],
    "Java": ["Java is popular"],
    "popular": ["Java is popular"],
    "easy": ["Python is easy"]
}
```

**Problem 3:** Write a function that takes a list of order items and applies tiered pricing: first 5 units at full price, next 5 at 10% off, remaining at 20% off.
```
Input:  [{"item": "Widget", "qty": 12, "price": 100}]
Output: {
    "item": "Widget",
    "breakdown": [
        {"units": 5, "price": 100, "subtotal": 500},
        {"units": 5, "price": 90, "subtotal": 450},
        {"units": 2, "price": 80, "subtotal": 160}
    ],
    "total": 1110
}
```

**Problem 4:** Write a function that takes a configuration dictionary and an override dictionary, and deep-merges them with the override taking precedence. Support nested dicts and list appending.
```
Input:  config = {"db": {"host": "localhost", "port": 5432}, "debug": False, "plugins": ["auth"]}
        override = {"db": {"port": 3306}, "debug": True, "plugins": ["cache"]}
Output: {"db": {"host": "localhost", "port": 3306}, "debug": True, "plugins": ["auth", "cache"]}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 101         | 5000   | 2024-01-10 |
| 3        | 102         | 8000   | 2024-01-20 |
| 4        | 101         | 3000   | 2024-02-05 |
| 7        | 103         | 12000  | 2024-02-15 |
| 8        | 102         | 6000   | 2024-03-01 |

**Table: sales**
| sale_id | salesperson | amount | sale_month |
|---------|-------------|--------|------------|
| 1       | Ravi        | 15000  | Jan        |
| 2       | Ravi        | 20000  | Feb        |
| 3       | Ravi        | 18000  | Mar        |
| 4       | Priya       | 12000  | Jan        |
| 5       | Priya       | 16000  | Feb        |
| 6       | Priya       | 22000  | Mar        |

**Table: customers**
| customer_id | name   | total_orders |
|-------------|--------|--------------|
| 101         | Ravi   | 55000        |
| 102         | Priya  | 25000        |
| 103         | Karan  | 8000         |
| 104         | Meena  | 15000        |

**Problem 1:** Write a SQL query to find the customer with the highest total order amount.

**Problem 2:** Write a SQL query to find the total sales amount per salesperson.

**Problem 3:** Write a SQL query to classify customers as 'Gold' (total orders > 50000), 'Silver' (20000-50000), or 'Bronze' (< 20000) and count customers in each tier.

### Part D — OOP Based Problem

Design an event management system:
- `Event` class with `event_id`, `name`, `date`, `venue`, `max_capacity`, `ticket_price`
- `Attendee` class with `attendee_id`, `name`, `email`, `events_registered` (list)
- `EventManager` class with:
  - `create_event(name, date, venue, capacity, price)`
  - `register_attendee(attendee, event_id)` — check capacity, add to event
  - `cancel_registration(attendee_id, event_id)`
  - `event_revenue(event_id)` — tickets sold × price
  - `upcoming_events()` — events with date >= today
  - `event_report(event_id)` — details, attendees list, tickets sold, tickets available, revenue
- Handle: over-capacity registration, duplicate registration, cancelling non-existent registration
- Demonstrate full flow with 3 events and 5 attendees

### Part E — Django Based Problem

Build a DRF API for a Student Performance Tracker:
- Models: `Course` (name, code unique, credits, instructor_name) and `Enrollment` (student_name, student_id, course FK, grade CharField nullable, semester, year)
- Course serializer shows enrolled student count
- Enrollment serializer shows course name
- ViewSets for both models
- Custom actions:
  - `GET /courses/{id}/students/` — list all enrolled students with grades
  - `POST /enrollments/{id}/grade/` — assign grade to an enrollment
  - `GET /courses/{id}/stats/` — returns average grade, pass rate, top student
- Filter enrollments by semester, year, grade
- Prevent duplicate enrollment (same student + same course + same semester)
