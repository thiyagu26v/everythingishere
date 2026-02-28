# 📝 Question Paper 11 — Advanced 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `@staticmethod` and `@classmethod`? When would you use each?
2. How does Django handle form validation? Explain `is_valid()` and `cleaned_data`.
3. What is the difference between `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, and `FULL OUTER JOIN`? Give examples.
4. What are Python closures? Explain with a simple example.
5. What is the difference between `GenericAPIView` and `ViewSet` in DRF?
6. What are Python's `*args` and `**kwargs`? How do they work together?
7. What is a database index? How does it improve query performance?
8. What is Django's `ContentType` framework? Give a simple use case.
9. Explain the difference between `select_related()` and `prefetch_related()` in Django ORM.
10. What are environment variables? Why are they important in Django projects?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python protocol must a class implement to be used in a `with` statement?
2. What SQL keyword is used to check for NULL values?
3. What DRF class is used to define custom permission logic?
4. What Python module provides thread-safe queue implementations?
5. What Django signal is fired after a model instance is saved?
6. What HTTP header is used for content negotiation (requesting specific response format)?
7. What SQL technique is used to combine hierarchical data (parent-child) into a flat result?
8. What Python module provides support for abstract base classes?
9. What is the name of the pattern where an object's behavior changes based on its internal state?
10. What Django setting controls which database routers are used?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of transaction dictionaries (each with `type`: "credit"/"debit", `amount`, `date`) and returns the running balance after each transaction, starting from an initial balance.
```
Input:  initial_balance = 10000
        transactions = [
            {"type": "credit", "amount": 5000, "date": "2025-01-01"},
            {"type": "debit", "amount": 3000, "date": "2025-01-02"},
            {"type": "debit", "amount": 8000, "date": "2025-01-03"}
        ]
Output: [
    {"date": "2025-01-01", "balance": 15000},
    {"date": "2025-01-02", "balance": 12000},
    {"date": "2025-01-03", "balance": 4000}
]
```

**Problem 2:** Write a custom iterator class `DateRange` that takes a `start_date` and `end_date` and iterates over all dates in the range. It should support `for date in DateRange(start, end)` syntax.
```
from datetime import date
for d in DateRange(date(2025, 1, 1), date(2025, 1, 4)):
    print(d)

Output:
2025-01-01
2025-01-02
2025-01-03
2025-01-04
```

**Problem 3:** Write a function that takes a list of student records (name, subject, marks) and returns a report card: for each student, show all subjects with marks, total, percentage, and grade (A/B/C/D/F).
```
Input:  [
    {"name": "Ravi", "subject": "Math", "marks": 85},
    {"name": "Ravi", "subject": "Science", "marks": 90},
    {"name": "Priya", "subject": "Math", "marks": 70},
    {"name": "Priya", "subject": "Science", "marks": 65}
]
Output: {
    "Ravi": {"subjects": {"Math": 85, "Science": 90}, "total": 175, "percentage": 87.5, "grade": "A"},
    "Priya": {"subjects": {"Math": 70, "Science": 65}, "total": 135, "percentage": 67.5, "grade": "B"}
}
```

**Problem 4:** Write a function that compares two JSON-like dictionaries and returns the differences: keys added, keys removed, and keys with changed values.
```
Input:  old = {"name": "Ravi", "age": 25, "city": "Chennai"}
        new = {"name": "Ravi", "age": 26, "state": "TN"}
Output: {"added": ["state"], "removed": ["city"], "changed": {"age": {"old": 25, "new": 26}}}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: orders**
| order_id | customer_name | amount  | order_date |
|----------|---------------|---------|------------|
| 1        | Ravi          | 5000    | 2024-01-10 |
| 2        | Priya         | 3500    | 2024-01-12 |
| 4        | Karan         | 7200    | 2024-01-15 |
| 5        | Meena         | 2800    | 2024-01-18 |
| 8        | Arjun         | 6100    | 2024-01-20 |

**Table: employees**
| emp_id | name   | department | salary | manager_id |
|--------|--------|------------|--------|------------|
| 1      | CEO    | Exec       | 200000 | NULL       |
| 2      | Ravi   | IT         | 70000  | 1          |
| 3      | Priya  | IT         | 60000  | 2          |
| 4      | Karan  | HR         | 55000  | 1          |
| 5      | Meena  | HR         | 45000  | 4          |

**Problem 1:** Write a SQL query to find all orders with an amount greater than the average order amount.

**Problem 2:** Write a SQL query using a self-join to find employees and their managers (showing employee name and manager name).

**Problem 3:** Write a SQL query to find the department with the highest total salary.

### Part D — OOP Based Problem

Design a notification system:
- `Notification` base class with `recipient`, `message`, `timestamp`, `is_read`
- `EmailNotification` - has `email_address`, `send()` method
- `SMSNotification` - has `phone_number`, `send()` method
- `NotificationManager` class:
  - `send_notification(notification)` — sends and stores notification
  - `get_unread(recipient)` — returns all unread notifications for a person
  - `mark_as_read(notification_id)`
  - `get_all(recipient)` — returns all notifications for a person
- Create 3 email and 2 SMS notifications, demonstrate sending, reading, and marking as read

### Part E — Django Based Problem

Build a complete REST API for a Task Management System:
- Models: `Project` (name, description, owner FK to User, created_at), `Task` (title, description, project FK, assigned_to FK to User, status choices: todo/in_progress/done/blocked, priority choices: low/medium/high/urgent, due_date, created_at, updated_at)
- Nested routes: `/projects/{id}/tasks/` to list/create tasks for a project
- Custom permissions: Only project owner can delete the project. Only assigned user or project owner can update tasks.
- Custom action: `POST /tasks/{id}/assign/` — assign a task to a user
- Filtering: by status, priority, assigned_to, due_date range
- Add a `GET /projects/{id}/stats/` endpoint that returns: total tasks, tasks by status, overdue tasks count
