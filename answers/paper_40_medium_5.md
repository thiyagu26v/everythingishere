# 📝 Question Paper 40 — Medium 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the `os` module in Python? Name 3 useful functions.
2. What are Django custom template filters? How do you create one?
3. What is the difference between `INNER JOIN` and `NATURAL JOIN` in SQL?
4. What is method chaining in Python? Give an example.
5. What is the difference between `@api_view` and `APIView` in DRF?
6. What is a Python `namedtuple`? How is it different from a regular tuple?
7. What is an SQL `VIEW`? Give a simple example of when you would use one.
8. What are Django model validators? How do you add a custom validator?
9. What is the `json` module in Python? How do you convert between Python dictionaries and JSON strings?
10. What is idempotency in APIs? Which HTTP methods are idempotent?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function creates an immutable version of a set?
2. What SQL keyword defines a check constraint?
3. What DRF feature automatically generates API documentation?
4. What Python method removes trailing whitespace from a string?
5. What HTTP status code means "Accepted"?
6. What built-in function chains multiple iterables together?
7. What SQL keyword starts a transaction?
8. What Django method deletes records matching a filter?
9. What Python keyword passes execution to a loop or function body without doing anything?
10. What does `OAuth` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that generates a report card from a dictionary of students and their subject marks. Calculate total, percentage, and assign grades.
```
Input:  {
    "Ravi": {"Math": 85, "Science": 78, "English": 92},
    "Priya": {"Math": 65, "Science": 70, "English": 60}
}
Output: {
    "Ravi": {"total": 255, "percentage": 85.0, "grade": "A"},
    "Priya": {"total": 195, "percentage": 65.0, "grade": "B"}
}
```

**Problem 2:** Write a function that takes two version strings and compares them. Return 1 if first is greater, -1 if second is greater, 0 if equal.
```
Input:  "1.2.3", "1.2.4"
Output: -1

Input:  "2.0.0", "1.9.9"
Output: 1
```

**Problem 3:** Write a function that encodes a string using run-length encoding, and another to decode it back.
```
encode("aaabbbccdd")   → "3a3b2c2d"
decode("3a3b2c2d")     → "aaabbbccdd"
```

**Problem 4:** Write a function that validates a password and returns specific feedback about what's missing.
```
Input:  "hello123"
Output: {"valid": False, "feedback": ["Need at least one uppercase letter", "Need at least one special character"]}

Input:  "Hello@123"
Output: {"valid": True, "feedback": []}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: users**
| user_id | name   | email              |
|---------|--------|--------------------|
| 1       | Ravi   | ravi@gmail.com     |
| 2       | Priya  | priya@yahoo.com    |
| 3       | Karan  | ravi@gmail.com     |

**Table: sales**
| sale_id | year | amount |
|---------|------|--------|
| 1       | 2022 | 500000 |
| 2       | 2023 | 650000 |
| 3       | 2024 | 780000 |

**Table: products**
| product_id | name     | price | category    |
|------------|----------|-------|-------------|
| 1          | Laptop   | 50000 | Electronics |
| 2          | Mouse    | 500   | Electronics |
| 3          | Monitor  | 48000 | Electronics |
| 4          | Pen      | 20    | Stationery  |

**Problem 1:** Write a SQL query to find duplicate email addresses in the `users` table.

**Problem 2:** Write a SQL query to find the total sales for each year from the `sales` table.

**Problem 3:** Write a SQL query to find all products whose price is within 10% of the maximum price.

### Part D — OOP Based Problem

Design a simple budget tracker:
- `Transaction` class with `description`, `amount`, `type` (income/expense), `category`, `date`
- `BudgetTracker` class with:
  - `add_transaction(description, amount, type, category)` 
  - `balance()` — total income minus total expenses
  - `summary_by_category()` — spending per category
  - `monthly_report(month, year)` — income, expenses, savings for a specific month
  - `top_expenses(n)` — top N highest expenses
  - `category_budget(category, limit)` — sets a budget limit for a category
  - `check_budget(category)` — returns if spending is within budget
- Demonstrate: add 10 transactions, set budgets, show reports and alerts

### Part E — Django Based Problem

Build a DRF API for an Inventory System:
- Model: `InventoryItem` with fields: `name`, `sku` (unique CharField), `quantity` (IntegerField), `unit_price` (DecimalField), `category` (CharField), `reorder_level` (IntegerField), `supplier` (CharField), `last_restocked` (DateField nullable)
- ViewSet with full CRUD
- Custom actions:
  - `POST /inventory/{id}/restock/` — accepts `quantity` to add, updates last_restocked to today
  - `GET /inventory/low-stock/` — returns items where quantity <= reorder_level
- Filter by category, supplier
- Search by name, sku
- Ordering by quantity, name, unit_price
