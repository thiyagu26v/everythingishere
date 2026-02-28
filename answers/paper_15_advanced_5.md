# 📝 Question Paper 15 — Advanced 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the `@property` decorator in Python? How does it work with getters and setters?
2. How does Django handle database relationships? Explain OneToOne, ForeignKey, and ManyToMany with examples.
3. What are SQL transactions? Explain `COMMIT` and `ROLLBACK` with an example.
4. What is encapsulation in Python? Give a simple example.
5. How does DRF handle permissions? What are the built-in permission classes?
6. What is the difference between `deepcopy` and `copy` in Python? When would you need deep copy?
7. What is database migration? How does Django handle it? What happens when you modify a model?
8. How does Django's signals framework work? Give examples of `pre_save` and `post_save`.
9. What is API versioning? Why is it important? (Just explain the concept simply)
10. What is the difference between REST API and a SOAP API at a high level?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method allows a class instance to be called like a function?
2. What SQL keyword is used to create a copy/backup of a table?
3. What DRF component sits between the view and the serializer to modify the queryset?
4. What Python library is commonly used for data validation?
5. What Django signal is fired before a model's `delete()` method is executed?
6. What HTTP status code indicates the server understood the request but refuses to authorize it?
7. What SQL keyword is used to create an index on a table?
8. What Python tool checks your code for syntax errors and style issues?
9. What DRF mechanism allows overriding the object-level permission check?
10. What is the difference between a monolithic and a microservices architecture at a high level?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of employee attendance records (name, date, check_in, check_out) and returns a monthly report: total working hours per employee, average daily hours, days absent, and late arrivals (after 9:30 AM).
```
Input:  [
    {"name": "Ravi", "date": "2025-01-01", "check_in": "09:15", "check_out": "18:00"},
    {"name": "Ravi", "date": "2025-01-02", "check_in": "09:45", "check_out": "17:30"},
    {"name": "Priya", "date": "2025-01-01", "check_in": "09:00", "check_out": "18:30"}
]
Output: {
    "Ravi": {"total_hours": 16.5, "avg_daily_hours": 8.25, "days_present": 2, "late_arrivals": 1},
    "Priya": {"total_hours": 9.5, "avg_daily_hours": 9.5, "days_present": 1, "late_arrivals": 0}
}
```

**Problem 2:** Write a function that takes two versions of a text (as strings) and generates a simple diff showing which lines were added, removed, or unchanged.
```
Input:  old_text = "line1\nline2\nline3\nline4"
        new_text = "line1\nline2 modified\nline3\nline5"
Output: [
    {"line": "line1", "status": "unchanged"},
    {"line": "line2", "status": "removed"},
    {"line": "line2 modified", "status": "added"},
    {"line": "line3", "status": "unchanged"},
    {"line": "line4", "status": "removed"},
    {"line": "line5", "status": "added"}
]
```

**Problem 3:** Write a function that takes a list of dictionaries representing sales data and generates a pivot table: rows are products, columns are months, values are total sales.
```
Input:  [
    {"product": "Laptop", "month": "Jan", "amount": 50000},
    {"product": "Laptop", "month": "Feb", "amount": 60000},
    {"product": "Phone", "month": "Jan", "amount": 30000},
    {"product": "Phone", "month": "Jan", "amount": 20000}
]
Output: {
    "Laptop": {"Jan": 50000, "Feb": 60000},
    "Phone": {"Jan": 50000, "Feb": 0}
}
```

**Problem 4:** Write a function that takes a dictionary with expected types and validates whether given data matches those types. Return a list of errors.
```
schema = {"name": str, "age": int, "email": str}
data = {"name": "Ravi", "age": "twenty", "email": "ravi@mail.com"}
Output: ["age: expected int, got str"]

data = {"name": "Ravi", "age": 25, "email": "ravi@mail.com"}
Output: []  (no errors)
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: user_purchases**
| user_id | product_id |
|---------|------------|
| 1       | 101        |
| 1       | 102        |
| 2       | 101        |
| 2       | 103        |
| 3       | 101        |
| 3       | 102        |

**Table: products**
| id  | name     | category    |
|-----|----------|-------------|
| 101 | Laptop   | Electronics |
| 102 | Mouse    | Electronics |
| 103 | Notebook | Stationery  |

**Table: user_activity**
| user_id | action     | activity_date |
|---------|------------|---------------|
| 1       | signup     | 2024-01-01    |
| 1       | login      | 2024-01-05    |
| 2       | signup     | 2024-01-03    |
| 2       | login      | 2024-01-10    |
| 3       | signup     | 2024-01-15    |

**Table: roles**
| id | name    | parent_id |
|----|---------|-----------|
| 1  | Admin   | NULL      |
| 2  | Manager | 1         |
| 3  | Staff   | 2         |

**Table: permissions**
| role_id | resource | action |
|---------|----------|--------|
| 1       | users    | delete |
| 2       | reports  | view   |
| 3       | tasks    | create |

**Problem 1:** Write a SQL query to find users who purchased products from both 'Electronics' and 'Stationery' categories.

**Problem 2:** Write a SQL query to find users who signed up but never logged in (using the `user_activity` table).

**Problem 3:** Write a SQL query to find all child roles of 'Admin' using the `roles` table (showing role name and parent name).

### Part D — OOP Based Problem

Design a simple **Inventory Management System**:
- `Product` class with `product_id`, `name`, `category`, `price`, `stock_quantity`
- `Warehouse` class:
  - `add_product(product)` — add a product to inventory
  - `restock(product_id, quantity)` — add stock
  - `sell(product_id, quantity)` — reduce stock if available
  - `get_low_stock(threshold)` — products below threshold
  - `get_total_value()` — total value of all inventory (price × quantity)
  - `search(keyword)` — search by name or category
  - `sales_report()` — total items sold, revenue generated
- Handle: selling more than available stock, restocking non-existent product
- Demonstrate with 5 products, multiple sale and restock operations

### Part E — Django Based Problem

Build a complete **Job Board API** with advanced features:
- Models:
  - `Company` (name, slug, description, logo_url, website, is_verified, created_at)
  - `JobPosting` (company FK, title, slug, description, requirements as JSONField, location, salary_min, salary_max, job_type choices: full_time/part_time/contract/remote, experience_level choices: junior/mid/senior, is_active, posted_at, expires_at)
  - `Application` (job FK, applicant FK User, cover_letter, resume_url, status choices: pending/reviewed/shortlisted/rejected/accepted, applied_at, updated_at)
  - `SavedJob` (user FK, job FK, saved_at)
- Endpoints:
  - Full CRUD for Companies (only verified companies can post jobs)
  - Full CRUD for JobPostings (only company owner can manage)
  - `POST /jobs/{id}/apply/` — apply to a job (one application per user per job)
  - `GET /jobs/{id}/applications/` — only company owner can view
  - `PATCH /applications/{id}/status/` — update application status
  - `POST /jobs/{id}/save/` and `DELETE /jobs/{id}/save/` — save/unsave jobs
  - `GET /saved-jobs/` — list user's saved jobs
  - `GET /jobs/recommended/` — recommend jobs based on user's application history (matching job_type and experience_level)
- Advanced features:
  - Full-text search on title, description, requirements
  - Filter by location, job_type, experience_level, salary range, posted within last N days
  - Pagination with count
  - Auto-expire job postings past `expires_at`
  - Email notification stub when application status changes
