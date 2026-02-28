# 📝 Question Paper 25 — Medium 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `@property` and a regular method in Python?
2. What is Django's `select_related`? How is it different from `prefetch_related`?
3. What is the difference between `DELETE` and `TRUNCATE` in SQL?
4. What is the `self` keyword in Python? Why is it needed in methods?
5. What are viewsets and routers in DRF? How do they simplify API development?
6. What is the `datetime` module in Python? How do you get today's date?
7. What is the difference between `CASCADE`, `SET_NULL`, and `PROTECT` in Django's `on_delete`?
8. What is SQL injection? How does Django ORM prevent it?
9. What is a Python `set`? Name 3 operations you can perform on sets.
10. What is the difference between a relational and a non-relational database?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method returns a copy of a list?
2. What SQL keyword creates a new database?
3. What DRF view class provides list and create functionality?
4. What Python function converts a dictionary to a list of tuples?
5. What HTTP status code means "Service Unavailable"?
6. What built-in function filters elements based on a condition?
7. What SQL function extracts the year from a date column?
8. What Django ORM method returns the count of matching records?
9. What Python keyword makes a variable accessible globally?
10. What does `ACID` stand for in databases?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of transactions (positive for income, negative for expenses) and returns a monthly summary: total income, total expenses, net balance, and the largest expense.
```
Input:  [5000, -1200, -800, 3000, -500, -2000, 1000]
Output: {
    "total_income": 9000,
    "total_expenses": 4500,
    "net_balance": 4500,
    "largest_expense": 2000
}
```

**Problem 2:** Write a function that converts a Roman numeral string to an integer.
```
Input:  "XIV"
Output: 14

Input:  "MCMXCIV"
Output: 1994
```

**Problem 3:** Write a function that takes a list of file names and groups them by extension. Files without extensions go under "no_extension".
```
Input:  ["app.py", "data.csv", "readme.md", "script.py", "photo.jpg", "notes", "test.csv"]
Output: {"py": ["app.py", "script.py"], "csv": ["data.csv", "test.csv"], "md": ["readme.md"], "jpg": ["photo.jpg"], "no_extension": ["notes"]}
```

**Problem 4:** Write a function that takes a matrix (2D list) and returns its transpose.
```
Input:  [[1, 2, 3], [4, 5, 6]]
Output: [[1, 4], [2, 5], [3, 6]]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: products**
| product_id | name     | price |
|------------|----------|-------|
| 1          | Laptop   | 50000 |
| 2          | Mouse    | 500   |
| 3          | Keyboard | 1500  |

**Table: order_items**
| item_id | order_id | product_id | quantity |
|---------|----------|------------|----------|
| 1       | 1        | 1          | 2        |
| 2       | 2        | 1          | 1        |
| 3       | 3        | 2          | 5        |
| 4       | 4        | 3          | 3        |
| ...     | ...      | ...        | ...      |
(assume 12+ orders for product 1)

**Table: orders**
| order_id | customer_id | total_amount | order_date |
|----------|-------------|--------------|------------|
| 1        | 101         | 5000         | 2024-01-10 |
| 2        | 102         | 3000         | 2024-01-15 |
| 3        | 103         | 8000         | 2024-02-01 |
| 4        | 101         | 2000         | 2024-02-20 |

**Table: employee_sales**
| emp_id | name   | quarter | sales_total |
|--------|--------|---------|-------------|
| 1      | Ravi   | Q1      | 50000       |
| 1      | Ravi   | Q2      | 60000       |
| 1      | Ravi   | Q3      | 45000       |
| 2      | Priya  | Q1      | 40000       |
| 2      | Priya  | Q2      | 55000       |

**Problem 1:** Write a SQL query using `GROUP BY` and `HAVING` to find products that have been ordered more than 10 times.

**Problem 2:** Write a SQL query to find orders where the order total is above the overall average order total.

**Problem 3:** Write a SQL query to show each salesperson's name and their total sales across all months.

### Part D — OOP Based Problem

Design a parking lot system:
- `Vehicle` class with `plate_number`, `vehicle_type` (car/bike/truck)
- `ParkingSpot` class with `spot_id`, `spot_type`, `is_occupied`, `vehicle`
- `ParkingLot` class with:
  - Initialize with a fixed number of spots per type
  - `park_vehicle(vehicle)` — find available spot matching type, park it
  - `remove_vehicle(plate_number)` — free the spot
  - `available_spots()` — returns count by type
  - `find_vehicle(plate_number)` — returns spot details
- Handle: parking a vehicle when no spots available, removing non-existent vehicle
- Demonstrate the system

### Part E — Django Based Problem

Build a DRF API for a Notes app:
- Model: `Note` with fields: `title`, `content`, `color` (choices: yellow, blue, green, pink, white), `is_pinned` (BooleanField), `tags` (CharField, comma-separated), `created_at`, `updated_at`
- Full CRUD via ViewSet
- Custom action: `POST /notes/{id}/pin/` to toggle pin status
- Pinned notes should always appear first in listing
- Filter by color, is_pinned
- Search by title, content, tags
