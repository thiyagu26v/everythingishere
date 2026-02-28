# 📝 Question Paper 26 — Advanced 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `classmethod` and `staticmethod`? When would you use each one?
2. How does Django's ORM handle database transactions? Explain `atomic()`.
3. What is the difference between a `PRIMARY KEY` and a `UNIQUE` constraint in SQL?
4. What are context managers in Python? How do you create one using `__enter__` and `__exit__`?
5. What is the difference between session-based and token-based authentication in DRF?
6. What is the `random` module in Python? Name 3 useful functions from it.
7. What is a SQL `VIEW`? When would you use one?
8. What are Django model managers? How do you create a custom manager?
9. What is the difference between `pickle` and `json` for serialization in Python?
10. What is CORS? How do you configure it in a Django project?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python keyword is used to create a class that inherits from another?
2. What SQL clause restricts the rows returned after grouping?
3. What DRF permission class allows only authenticated users?
4. What Python method checks if a string contains only alphabets?
5. What HTTP status code means "Created"?
6. What built-in function converts a list of characters to a string?
7. What SQL function returns the current date and time?
8. What Django ORM method returns only the first matching record?
9. What Python module provides date and time handling?
10. What does `WSGI` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of dictionaries representing expenses (amount, category, date) and returns a monthly breakdown: each month's total spending, top category, and daily average.
```
Input:  [
    {"amount": 500, "category": "food", "date": "2025-01-05"},
    {"amount": 1200, "category": "rent", "date": "2025-01-10"},
    {"amount": 300, "category": "food", "date": "2025-01-20"},
    {"amount": 800, "category": "transport", "date": "2025-02-15"}
]
Output: {
    "2025-01": {"total": 2000, "top_category": "food", "daily_avg": 64.52},
    "2025-02": {"total": 800, "top_category": "transport", "daily_avg": 28.57}
}
```

**Problem 2:** Write a function that takes a phone number in any format and standardizes it to a consistent format.
```
Input:  "+91 98765 43210"
Output: "+919876543210"

Input:  "098765-43210"
Output: "+919876543210"

Input:  "9876543210"
Output: "+919876543210"
```

**Problem 3:** Write a function that takes a list of employee schedules (name, start_time, end_time) and returns who is working at a given time.
```
Input:  schedules = [
    {"name": "Ravi", "start": "09:00", "end": "17:00"},
    {"name": "Priya", "start": "10:00", "end": "18:00"},
    {"name": "Karan", "start": "14:00", "end": "22:00"}
], check_time = "15:00"
Output: ["Ravi", "Priya", "Karan"]
```

**Problem 4:** Write a function that recursively searches a nested dictionary for a given key and returns all matching values.
```
Input:  data = {"a": 1, "b": {"c": 2, "d": {"a": 3, "e": {"a": 4}}}}, key = "a"
Output: [1, 3, 4]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: order_items**
| item_id | order_id | product_id | quantity | price |
|---------|----------|------------|----------|-------|
| 1       | 1        | 101        | 3        | 500   |
| 2       | 2        | 102        | 5        | 200   |
| 3       | 3        | 101        | 2        | 500   |
| 4       | 4        | 103        | 1        | 1500  |
| 5       | 5        | 102        | 4        | 200   |

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 70000  |
| 2      | Priya  | IT         | 55000  |
| 3      | Karan  | HR         | 48000  |
| 4      | Meena  | HR         | 52000  |
| 5      | Arjun  | Sales      | 60000  |
| 6      | Divya  | Sales      | 45000  |

**Problem 1:** Write a SQL query to find the most popular product (highest total quantity sold) from the `order_items` table.

**Problem 2:** Write a SQL query to show each employee's salary and what percentage it is of the total salary bill.

**Problem 3:** Write a SQL query to find employees who earn more than the average salary in their department.

### Part D — OOP Based Problem

Design an online food ordering system:
- `MenuItem` class with `name`, `price`, `category` (starter/main/dessert/drink), `is_available`
- `Order` class with:
  - `add_item(menu_item, quantity)`, `remove_item(menu_item_name)`
  - `subtotal()`, `apply_discount(percentage)`, `calculate_tax(18%)`, `total()`
  - `order_summary()` — formatted receipt with all items, quantities, prices, subtotal, discount, tax, total
- Handle: adding unavailable items, removing items not in order
- `Menu` class that holds all items and has `search(name)`, `filter_by_category(cat)`, `available_items()`
- Demonstrate full flow

### Part E — Django Based Problem

Build a DRF API for a Task Manager:
- Model: `Task` with fields: `title`, `description`, `priority` (choices: low/medium/high/urgent), `status` (choices: todo/in_progress/done/cancelled), `due_date`, `assigned_to` (CharField), `created_at`, `updated_at`
- Full CRUD via ViewSet
- Custom action: `PATCH /tasks/{id}/status/` that accepts only a `status` field
- Filter by priority, status, assigned_to
- Overdue tasks endpoint: `GET /tasks/overdue/` — returns tasks where due_date < today and status != done
- Ordering by priority, due_date, created_at
