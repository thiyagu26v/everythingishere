# 📝 Question Paper 43 — Advanced 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the `__str__` method in Python? How does it differ from `__repr__`?
2. What is Django middleware? Name 3 built-in middleware classes and what they do.
3. What is the difference between `RANK()` and `DENSE_RANK()` in SQL window functions?
4. What is method overriding in Python? Give a simple example.
5. What are DRF permissions? Name 3 built-in permission classes and explain each.
6. What is the `re` module in Python? Name 4 commonly used regex functions.
7. What is database denormalization? When would you choose it over normalization?
8. What are Django's `values()` and `values_list()`? What's the difference?
9. What is the difference between `==` and `is` in Python? Explain with mutable objects.
10. What is API documentation? What tools do you know for documenting REST APIs?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function returns the hash value of an object?
2. What SQL keyword specifies the order of sorted results?
3. What DRF setting controls the default pagination page size?
4. What Python method converts a JSON string to a Python object?
5. What HTTP status code means "Gone"?
6. What built-in function evaluates a string as a Python expression?
7. What SQL function returns the position of a substring?
8. What Django method gets a single object by conditions?
9. What Python keyword ensures a block of code always runs?
10. What does `NGINX` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of e-commerce orders (order_id, customer, items list, status) and generates an analytics report: total revenue, average order value, most popular item, order status distribution, and top customer.
```
Input:  [
    {"order_id": 1, "customer": "Ravi", "items": [{"name": "Pen", "price": 20, "qty": 5}], "status": "delivered"},
    {"order_id": 2, "customer": "Ravi", "items": [{"name": "Book", "price": 200, "qty": 2}, {"name": "Pen", "price": 20, "qty": 3}], "status": "delivered"},
    {"order_id": 3, "customer": "Priya", "items": [{"name": "Book", "price": 200, "qty": 1}], "status": "pending"}
]
Output: {
    "total_revenue": 760,
    "avg_order_value": 253.33,
    "most_popular_item": "Pen",
    "status_dist": {"delivered": 2, "pending": 1},
    "top_customer": {"name": "Ravi", "total_spent": 560}
}
```

**Problem 2:** Write a function that takes a list of dates as strings and returns the dates grouped by month.
```
Input:  ["2025-01-05", "2025-01-20", "2025-02-10", "2025-03-15", "2025-02-28"]
Output: {
    "January": ["2025-01-05", "2025-01-20"],
    "February": ["2025-02-10", "2025-02-28"],
    "March": ["2025-03-15"]
}
```

**Problem 3:** Write a function that takes two lists of dictionaries (old_data and new_data) both with `id` field, and returns: added records, removed records, and modified records (with before/after).
```
Input:  old = [{"id": 1, "name": "Ravi"}, {"id": 2, "name": "Priya"}]
        new = [{"id": 1, "name": "Ravi Kumar"}, {"id": 3, "name": "Karan"}]
Output: {
    "added": [{"id": 3, "name": "Karan"}],
    "removed": [{"id": 2, "name": "Priya"}],
    "modified": [{"id": 1, "before": {"name": "Ravi"}, "after": {"name": "Ravi Kumar"}}]
}
```

**Problem 4:** Write a function that takes a text template with `{variable}` placeholders and a data dictionary, and renders the template. Handle missing variables with a default value.
```
Input:  template = "Hello {name}, welcome to {company}. Your role is {role}."
        data = {"name": "Ravi", "company": "TechCo"}
        default = "N/A"
Output: "Hello Ravi, welcome to TechCo. Your role is N/A."
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: customers**
| customer_id | name   |
|-------------|--------|
| 1           | Ravi   |
| 2           | Priya  |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 1           | 5000   | 2024-01-01 |
| 2        | 1           | 3000   | 2024-01-02 |
| 3        | 1           | 7000   | 2024-01-03 |
| 4        | 1           | 2000   | 2024-01-05 |
| 5        | 2           | 4000   | 2024-01-10 |

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 70000  |
| 2      | Priya  | IT         | 55000  |
| 3      | Karan  | HR         | 48000  |
| 4      | Meena  | Sales      | 62000  |

**Table: monthly_sales**
| month      | total_sales |
|------------|-------------|
| 2024-01-01 | 500000      |
| 2024-02-01 | 620000      |
| 2024-03-01 | 580000      |

**Problem 1:** Write a SQL query to find the total order amount for each customer, showing customer name and total.

**Problem 2:** Write a SQL query to show each employee's name, salary, department, and how their salary compares to the department average (above/below/equal).

**Problem 3:** Write a SQL query to find the month with the highest total sales from the `monthly_sales` table.

### Part D — OOP Based Problem

Design a simple project management tool:
- `Task` class with `task_id`, `title`, `description`, `assigned_to`, `status` (todo/in_progress/done), `priority` (low/medium/high), `due_date`
- `Project` class with:
  - `name`, `tasks` (list), `team_members` (list)
  - `add_task(task)`, `assign_task(task_id, member)`
  - `update_status(task_id, status)`
  - `tasks_by_status(status)` — filter tasks
  - `tasks_by_member(member)` — tasks assigned to a member
  - `overdue_tasks()` — tasks past due_date that aren't done
  - `progress()` — percentage of completed tasks
  - `dashboard()` — summary: total tasks, status breakdown, overdue count, progress percentage
- Demonstrate: create project with 8 tasks, assign to 3 members, update statuses, show dashboard

### Part E — Django Based Problem

Build a DRF API for a Subscription Service:
- Models: `Plan` (name, description, price, duration_days, features TextField, is_active) and `Subscription` (user_name, email, plan FK, start_date, end_date, is_active, auto_renew BooleanField)
- Plan serializer shows subscriber count
- Subscription serializer shows plan details
- ViewSets for both
- Custom actions:
  - `POST /subscriptions/{id}/cancel/` — sets is_active to False, auto_renew to False
  - `POST /subscriptions/{id}/renew/` — extends end_date by plan's duration_days
  - `GET /subscriptions/expiring-soon/` — subscriptions expiring within 7 days
- Filter by is_active, plan
- Prevent subscribing to inactive plans
