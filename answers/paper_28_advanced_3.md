# 📝 Question Paper 28 — Advanced 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the `__repr__` vs `__str__` method? When would you define both?
2. What is Django's `Q` object? Give an example with OR and AND conditions.
3. What is the difference between `INNER JOIN` and `LEFT JOIN` in SQL? Give examples.
4. What is duck typing in Python? Give a practical example.
5. What is throttling in DRF? How do you configure different rates for different users?
6. What is the `collections.defaultdict`? How is it different from a regular dict?
7. What are database constraints? Explain CHECK, UNIQUE, and NOT NULL.
8. How does Django's URL dispatcher work? Explain `path()` vs `re_path()`.
9. What is the difference between `copy()` and `deepcopy()` for nested objects?
10. What is API rate limiting? Why is it important?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method splits a string into a list by a delimiter?
2. What SQL keyword defines a foreign key relationship?
3. What DRF class provides create, retrieve, update, and delete actions?
4. What Python function returns the memory address (identity) of an object?
5. What HTTP status code means "Method Not Allowed"?
6. What built-in function checks if an object is a subclass of a class?
7. What SQL keyword adds a constraint to an existing column?
8. What Django method creates and saves an object in one step?
9. What Python keyword defines a class?
10. What does `DNS` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of product sales (product_name, quantity, price, region) and generates a report: top-selling product per region, region with highest revenue, and overall total revenue.
```
Input:  [
    {"product": "Laptop", "qty": 5, "price": 50000, "region": "South"},
    {"product": "Phone", "qty": 10, "price": 20000, "region": "South"},
    {"product": "Laptop", "qty": 3, "price": 50000, "region": "North"},
    {"product": "Tablet", "qty": 8, "price": 15000, "region": "North"}
]
Output: {
    "top_per_region": {"South": "Laptop", "North": "Tablet"},
    "highest_revenue_region": "South",
    "total_revenue": 620000
}
```

**Problem 2:** Write a function that takes a URL string and extracts the domain name from it.
```
Input:  "https://www.example.com/api/users"
Output: "example.com"

Input:  "http://blog.site.co.in/posts"
Output: "site.co.in"
```

**Problem 3:** Write a function that implements a simple calculator that processes a list of operations sequentially from an initial value.
```
Input:  initial = 10, operations = [("add", 5), ("multiply", 3), ("subtract", 10), ("divide", 5)]
Output: 7.0  (10 → 15 → 45 → 35 → 7.0)
```

**Problem 4:** Write a function that takes a list of user activity logs and finds the most active users, their total time spent, and favorite activity.
```
Input:  [
    {"user": "Ravi", "activity": "coding", "duration": 60},
    {"user": "Ravi", "activity": "reading", "duration": 30},
    {"user": "Ravi", "activity": "coding", "duration": 45},
    {"user": "Priya", "activity": "reading", "duration": 90}
]
Output: {
    "Ravi": {"total_time": 135, "favorite_activity": "coding"},
    "Priya": {"total_time": 90, "favorite_activity": "reading"}
}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 101         | 15000  | 2024-01-10 |
| 2        | 102         | 8000   | 2024-01-20 |
| 3        | 101         | 22000  | 2024-02-05 |
| 4        | 103         | 5000   | 2024-02-15 |
| 5        | 102         | 12000  | 2024-03-01 |

**Table: products**
| product_id | name     | price |
|------------|----------|-------|
| 1          | Laptop   | 50000 |
| 2          | Mouse    | 500   |
| 3          | Keyboard | 1500  |
| 4          | Monitor  | 20000 |

**Table: employees**
| emp_id | name   | department |
|--------|--------|------------|
| 1      | Ravi   | IT         |
| 2      | Priya  | IT         |
| 3      | Karan  | HR         |
| 4      | Meena  | Sales      |
| 5      | Arjun  | HR         |

**Problem 1:** Write a SQL query to find the month with the highest sales from the `orders` table (using date functions and GROUP BY).

**Problem 2:** Write a SQL query to show each product's name, price, and the price difference from the most expensive product.

**Problem 3:** Write a SQL query to count the number of employees in each department and show department name with count.

### Part D — OOP Based Problem

Design a bank account system:
- `BankAccount` class with `account_number`, `holder_name`, `balance`
- `SavingsAccount(BankAccount)` — has interest rate, method to add monthly interest, minimum balance check
- `CurrentAccount(BankAccount)` — has overdraft limit, allows negative balance up to the limit
- Both have `deposit(amount)`, `withdraw(amount)`, `get_statement()` (last 5 transactions)
- `Bank` class with:
  - `create_account(type, name, initial_deposit)`
  - `transfer(from_acc, to_acc, amount)`
  - `total_deposits()` — total money across all accounts
- Demonstrate: create 2 accounts of each type, do deposits, withdrawals, transfer, show statements

### Part E — Django Based Problem

Build a DRF API for an E-commerce Product Catalog:
- Models: `Category` (name, description, parent FK to self for subcategories) and `Product` (name, description, price, stock, category FK, image_url, is_active, created_at)
- Category serializer should show subcategories nested
- Product ViewSet with full CRUD
- Filter products by category, price range, in_stock (stock > 0)
- Custom action: `GET /products/featured/` — returns top 5 products by stock
- Search by product name and description
- Pagination: 10 per page
