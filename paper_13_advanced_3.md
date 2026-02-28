# 📝 Question Paper 13 — Advanced 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What are Python class variables vs instance variables? How are they different?
2. How do you set up multiple databases in Django? When would you need it?
3. What are SQL subqueries? Give a simple example.
4. What is the Decorator pattern vs Python decorators? Explain the difference simply.
5. How does DRF content negotiation work? How do you return JSON vs HTML?
6. What is the difference between a list and a tuple in Python? When would you use each?
7. What is database normalization? Explain 1NF, 2NF, 3NF with simple examples.
8. What are Django's `F()` and `Q()` objects? When would you use them?
9. What is the difference between a `GET` request and a `POST` request?
10. What is the difference between PUT and PATCH HTTP methods? When to use which?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python module provides working with date/time in timezone-aware fashion?
2. What SQL technique combines multiple queries into a single round trip?
3. What DRF class provides automatic hyperlinking between related resources?
4. What Python built-in function returns a proxy object for calling parent class methods?
5. What Django template tag prevents Cross-Site Scripting (XSS)?
6. What HTTP status code means "Too Many Requests"?
7. What SQL concept groups a set of operations into a single unit of work?
8. What Python tool is used for code formatting (PEP 8 compliance)?
9. What DRF setting configures the default authentication scheme globally?
10. What design pattern provides a simplified interface to a complex subsystem?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that validates a dictionary against a schema. The schema defines field names, types, and whether they're required. Return a list of validation errors.
```
schema = {
    "name": {"type": str, "required": True},
    "age": {"type": int, "required": True},
    "email": {"type": str, "required": False}
}
Input:  {"name": "Ravi", "age": "twenty"}
Output: ["age: expected int, got str", "email: missing optional field"]

Input:  {"age": 25}
Output: ["name: required field missing"]
```

**Problem 2:** Write a function that takes a flat list of dictionaries with `id` and `parent_id` and builds a nested tree structure.
```
Input:  [
    {"id": 1, "name": "CEO", "parent_id": None},
    {"id": 2, "name": "CTO", "parent_id": 1},
    {"id": 3, "name": "Dev Lead", "parent_id": 2},
    {"id": 4, "name": "CFO", "parent_id": 1}
]
Output: {
    "id": 1, "name": "CEO", "children": [
        {"id": 2, "name": "CTO", "children": [
            {"id": 3, "name": "Dev Lead", "children": []}
        ]},
        {"id": 4, "name": "CFO", "children": []}
    ]
}
```

**Problem 3:** Write a function that takes two date ranges and determines the relationship: no overlap, partial overlap, or fully contained. If overlapping, return the overlapping date range.
```
Input:  ("2025-01-01", "2025-01-15"), ("2025-01-10", "2025-01-25")
Output: {"status": "partial_overlap", "overlap": ("2025-01-10", "2025-01-15")}

Input:  ("2025-01-01", "2025-01-30"), ("2025-01-05", "2025-01-10")
Output: {"status": "fully_contained", "overlap": ("2025-01-05", "2025-01-10")}
```

**Problem 4:** Write a function that takes a CSV string (with headers in the first row) and converts it to a list of dictionaries.
```
Input:  'name,city,bio\nRavi,Chennai,Developer\nPriya,Mumbai,Designer'
Output: [
    {"name": "Ravi", "city": "Chennai", "bio": "Developer"},
    {"name": "Priya", "city": "Mumbai", "bio": "Designer"}
]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: transactions**
| txn_id | account_id | type   | amount | txn_date   |
|--------|------------|--------|--------|------------|
| 1      | A001       | credit | 10000  | 2024-01-01 |
| 2      | A001       | debit  | 3000   | 2024-01-05 |
| 3      | A001       | debit  | 2000   | 2024-01-10 |
| 4      | A001       | credit | 5000   | 2024-01-15 |

**Table: attendance**
| emp_id | name  | attend_date |
|--------|-------|-------------|
| 1      | Ravi  | 2024-01-01  |
| 1      | Ravi  | 2024-01-02  |
| 1      | Ravi  | 2024-01-03  |
| 1      | Ravi  | 2024-01-05  |
| 1      | Ravi  | 2024-01-06  |

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 70000  |
| 2      | Priya  | IT         | 55000  |
| 3      | Karan  | HR         | 48000  |
| 4      | Meena  | HR         | 52000  |
| 5      | Arjun  | Sales      | 60000  |

**Problem 1:** Write a SQL query to find the total credit and debit amounts for each account.

**Problem 2:** Write a SQL query to find the employee who attended the most number of days.

**Problem 3:** Write a SQL query to find employees whose salary is above the average salary in their department.

### Part D — OOP Based Problem

Design a ticket booking system:
- `Event` class with `event_id`, `name`, `venue`, `total_seats`, `available_seats`, `date`
- `Ticket` class with `ticket_id`, `event`, `customer_name`, `seat_number`
- `BookingSystem` class:
  - `add_event(event)` — add a new event
  - `book_ticket(event_id, customer_name)` — book a ticket if seats available
  - `cancel_ticket(ticket_id)` — cancel and free the seat
  - `get_event_details(event_id)` — show event info with booked/available seats
  - `get_customer_tickets(customer_name)` — show all tickets for a customer
- Handle: overbooking, cancelling non-existent ticket
- Demonstrate with 2 events and 5 bookings

### Part E — Django Based Problem

Build an E-Commerce Product Catalog API:
- Models:
  - `Category` (name, slug, parent FK self for nested categories)
  - `Product` (name, slug, description, category FK, price, discount_price nullable, stock, is_active, created_at)
  - `ProductImage` (product FK, image_url, is_primary, order)
  - `Review` (product FK, user FK, rating 1-5, comment, created_at)
- Nested serializers: Product includes images and average rating
- Custom endpoints:
  - `GET /categories/tree/` — returns nested category tree
  - `GET /products/{id}/reviews/` — paginated reviews for a product
  - `POST /products/{id}/reviews/` — add review (one per user per product)
- Filtering: by category (including subcategories), price range, rating, in-stock only
- Search on product name and description

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [type(x).__name__ for x in [1, "hello", 3.14, True, [1]]]
print(result)
```
a) `[1, "hello", 3.14, True, [1]]`
b) `["int", "str", "float", "bool", "list"]`
c) `["number", "string", "decimal", "boolean", "array"]`
d) `["int", "str", "float", "int", "list"]`

**Q2 (MCQ):** What is the output?
```python
words = ["Python", "Java", "Go"]
result = [w.ljust(10, "*") for w in words]
print(result[0])
```
a) `"****Python"`
b) `"Python****"`
c) `"**Python**"`
d) `"Python    "`

**Q3 (MCQ):** What is the output?
```python
result = {x: [y for y in range(x)] for x in range(1, 4)}
print(result[3])
```
a) `[1, 2, 3]`
b) `[0, 1, 2]`
c) `3`
d) `[0, 1, 2, 3]`

**Q4 (Open-Ended):** What is the output?
```python
s = "abcabc"
result = {c: s.count(c) for c in set(s)}
print(sorted(result.items()))
```

**Q5 (Open-Ended):** What is the output?
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
result = [[row[i] for row in matrix] for i in range(3)]
print(result[1])
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
process = lambda s: "".join(c for c in s if c.isalpha())
print(process("h3ll0 w0rld!"))
```
a) `"h3ll0 w0rld!"`
b) `"hll wrld"`
c) `"hllwrld"`
d) `"350!"`

**Q7 (MCQ):** What is the output?
```python
data = [("a", 3), ("b", 1), ("c", 2)]
result = sorted(data, key=lambda x: x[1])
result2 = sorted(data, key=lambda x: x[0], reverse=True)
print(result[0], result2[0])
```
a) `("a", 3) ("c", 2)`
b) `("b", 1) ("c", 2)`
c) `("b", 1) ("a", 3)`
d) `("c", 2) ("a", 3)`

**Q8 (MCQ):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = list(map(lambda x: x, filter(lambda x: x > 2, nums)))
print(result)
```
a) `[1, 2, 3, 4, 5]`
b) `[3, 4, 5]`
c) `[1, 2]`
d) `[True, True, True]`

**Q9 (Open-Ended):** What is the output?
```python
from functools import reduce
data = [{"price": 100}, {"price": 200}, {"price": 150}]
total = reduce(lambda acc, x: acc + x["price"], data, 0)
print(total)
```

**Q10 (Open-Ended):** What is the output?
```python
dispatch = lambda action: {
    "greet": lambda: "Hello!",
    "bye": lambda: "Goodbye!",
}.get(action, lambda: "Unknown")()
print(dispatch("greet"))
print(dispatch("test"))
```
