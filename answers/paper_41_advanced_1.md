# 📝 Question Paper 41 — Advanced 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between a generator and an iterator in Python?
2. How does Django handle file uploads? What is `MEDIA_ROOT` and `MEDIA_URL`?
3. What is the difference between `INT` and `VARCHAR` data types in SQL?
4. What are Python's `__enter__` and `__exit__` methods? How do they relate to `with` statements?
5. What is the difference between `ListCreateAPIView` and `RetrieveUpdateDestroyAPIView` in DRF?
6. What is the `collections.OrderedDict`? When would you use it?
7. What is the difference between `COUNT(*)` and `COUNT(column)` in SQL?
8. What is Django's `get_queryset()` vs `get_object()` in views?
9. What is the `@staticmethod` vs `@classmethod` in practice? Give a real example of each.
10. What is rate limiting in APIs? How do you implement it?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function creates a list of tuples from multiple lists?
2. What SQL keyword creates a database trigger?
3. What DRF class provides automatic URL routing for ViewSets?
4. What Python method checks if a string is alphanumeric?
5. What HTTP status code means "Precondition Failed"?
6. What built-in function sums up all items in a list?
7. What SQL function removes leading and trailing spaces?
8. What Django method updates multiple records at once?
9. What Python keyword defines an abstract method?
10. What does `TLS` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a shopping cart (list of item dicts with name, price, quantity, category) and applies category-wise discounts: electronics 15%, clothing 20%, food 5%. Return the original total, discount breakdown by category, and final total.
```
Input:  [
    {"name": "Phone", "price": 20000, "qty": 1, "category": "electronics"},
    {"name": "Shirt", "price": 800, "qty": 2, "category": "clothing"},
    {"name": "Rice", "price": 200, "qty": 3, "category": "food"}
]
Output: {
    "original_total": 22200,
    "discounts": {"electronics": 3000, "clothing": 320, "food": 30},
    "final_total": 18850
}
```

**Problem 2:** Write a function that takes a list of file names with sizes (in bytes) and organizes them into size categories: "tiny" (< 1KB), "small" (1KB-1MB), "medium" (1MB-100MB), "large" (> 100MB).
```
Input:  [("readme.txt", 500), ("app.py", 15000), ("video.mp4", 150000000), ("data.csv", 5000000)]
Output: {
    "tiny": ["readme.txt"],
    "small": ["app.py"],
    "medium": ["data.csv"],
    "large": ["video.mp4"]
}
```

**Problem 3:** Write a function that takes a string containing mixed content and extracts all email addresses, phone numbers (10 digits), and URLs.
```
Input:  "Contact ravi@gmail.com or call 9876543210. Visit https://example.com for more."
Output: {
    "emails": ["ravi@gmail.com"],
    "phones": ["9876543210"],
    "urls": ["https://example.com"]
}
```

**Problem 4:** Write a function that implements a simple undo system. It should support `do(action, value)` and `undo()` operations on a starting value.
```
operations = UndoSystem(initial=10)
operations.do("add", 5)       → 15
operations.do("multiply", 3)  → 45
operations.do("subtract", 10) → 35
operations.undo()              → 45
operations.undo()              → 15
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: orders**
| order_id | customer_id | order_date |
|----------|-------------|------------|
| 1        | 101         | 2024-01-10 |
| 2        | 101         | 2024-02-15 |
| 3        | 102         | 2024-01-20 |
| 4        | 103         | 2024-03-05 |

**Table: order_items**
| item_id | order_id | product_id | quantity | price |
|---------|----------|------------|----------|-------|
| 1       | 1        | 1          | 2        | 500   |
| 2       | 1        | 2          | 1        | 200   |
| 3       | 2        | 3          | 3        | 150   |
| 4       | 3        | 1          | 1        | 500   |

**Table: customers**
| customer_id | name   |
|-------------|--------|
| 101         | Ravi   |
| 102         | Priya  |
| 103         | Karan  |

**Table: products**
| product_id | name     | category    |
|------------|----------|-------------|
| 1          | Laptop   | Electronics |
| 2          | Mouse    | Electronics |
| 3          | Notebook | Stationery  |

**Problem 1:** Write a SQL query to find all orders and their items using a JOIN, showing order_id, customer_name, product_name, quantity, and line total (price × quantity).

**Problem 2:** Write a SQL query to find customers who have placed more than one order, showing their name and number of orders.

**Problem 3:** Write a SQL query to find the most ordered product by total quantity.

### Part D — OOP Based Problem

Design a hospital appointment system:
- `Doctor` class with `doctor_id`, `name`, `specialization`, `available_slots` (list of time strings)
- `Patient` class with `patient_id`, `name`, `appointments` (list)
- `AppointmentSystem` class with:
  - `add_doctor(doctor)`, `add_patient(patient)`
  - `book_appointment(patient_id, doctor_id, slot)` — book if slot available
  - `cancel_appointment(patient_id, doctor_id, slot)`
  - `doctor_schedule(doctor_id)` — shows booked and available slots
  - `patient_appointments(patient_id)` — shows all appointments for a patient
  - `find_doctor_by_specialization(spec)` — find available doctors
- Handle: double booking, booking non-existent slot, cancelling non-existent appointment
- Demonstrate with 3 doctors, 4 patients

### Part E — Django Based Problem

Build a DRF API for a Job Board:
- Models: `Company` (name, description, website, location) and `Job` (company FK, title, description, salary_min, salary_max, job_type choices: full_time/part_time/contract/internship, experience_level choices: entry/mid/senior, is_active, posted_at, expires_at)
- Nested: company details shown in job listing
- ViewSets for both models
- Filter jobs by job_type, experience_level, salary range, company
- Custom action: `GET /jobs/search/?q=python&location=chennai` — search by title, description, company name, location
- Only show active, non-expired jobs in listing
- Ordering by posted_at, salary_max
