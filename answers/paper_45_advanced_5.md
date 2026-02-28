# 📝 Question Paper 45 — Advanced 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the `with` statement in Python? Give an example of using it with files.
2. What is Django's `select_related()` vs `prefetch_related()`? Give a practical scenario for each.
3. What is the difference between `COUNT(*)`, `COUNT(column)`, and `COUNT(DISTINCT column)` in SQL?
4. What are Python classes used for? Explain with a simple real-world example.
5. How does DRF handle authentication? Name 2 authentication methods.
6. What is the `pathlib` module in Python? How does it differ from `os.path`?
7. What is a database deadlock? How can it be prevented?
8. What is Django's `order_by()` method? How do you sort results in descending order?
9. What is the `json` module in Python? Explain `dumps()`, `loads()`, `dump()`, `load()`.
10. What is the difference between cookies and sessions in web development?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function creates an iterator that applies a function to every item?
2. What SQL function returns the current timestamp?
3. What DRF filter backend provides search functionality?
4. What Python method strips leading whitespace from a string?
5. What HTTP status code means "I'm a teapot" (an Easter egg)?
6. What built-in function determines if an object has an attribute?
7. What SQL clause limits results to a specific number?
8. What Django model field stores a boolean with NULL support?
9. What Python keyword creates an alias for an imported module?
10. What does `SDK` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of delivery orders (order_id, pickup_location, delivery_location, distance_km, weight_kg) and calculates shipping costs with rules: base rate ₹50, ₹10 per km, extra ₹5 per kg over 5kg, express delivery (distance < 10km) gets ₹20 surcharge.
```
Input:  [
    {"order_id": 1, "distance": 15, "weight": 3},
    {"order_id": 2, "distance": 5, "weight": 8},
    {"order_id": 3, "distance": 8, "weight": 2}
]
Output: [
    {"order_id": 1, "base": 50, "distance_charge": 150, "weight_charge": 0, "express": 0, "total": 200},
    {"order_id": 2, "base": 50, "distance_charge": 50, "weight_charge": 15, "express": 20, "total": 135},
    {"order_id": 3, "base": 50, "distance_charge": 80, "weight_charge": 0, "express": 20, "total": 150}
]
```

**Problem 2:** Write a function that takes a list of git-like commit messages and generates a changelog grouped by type: feat, fix, docs, refactor, test (parse from "type: message" format).
```
Input:  [
    "feat: add user login",
    "fix: resolve crash on submit",
    "feat: add dashboard",
    "docs: update README",
    "fix: fix typo in header",
    "refactor: clean up utils"
]
Output: {
    "Features": ["add user login", "add dashboard"],
    "Bug Fixes": ["resolve crash on submit", "fix typo in header"],
    "Documentation": ["update README"],
    "Refactoring": ["clean up utils"]
}
```

**Problem 3:** Write a function that simulates a simple bank transfer system: given a list of accounts with balances and a list of transfers, process all transfers and return final balances. Handle insufficient funds.
```
Input:  accounts = {"A": 1000, "B": 500, "C": 200}
        transfers = [("A", "B", 300), ("B", "C", 700), ("C", "A", 100)]
Output: {
    "final_balances": {"A": 800, "B": 500, "C": 100},
    "failed": [{"from": "B", "to": "C", "amount": 700, "reason": "Insufficient funds (balance: 500)"}]
}
```

**Problem 4:** Write a function that takes a list of match results (team_a, team_b, score_a, score_b) and generates a league table with: team name, matches played, wins, draws, losses, goals for, goals against, goal difference, and points (win=3, draw=1, loss=0).
```
Input:  [
    {"team_a": "India", "team_b": "Aus", "score_a": 2, "score_b": 1},
    {"team_a": "Eng", "team_b": "India", "score_a": 1, "score_b": 1},
    {"team_a": "Aus", "team_b": "Eng", "score_a": 0, "score_b": 3}
]
Output: sorted by points → [
    {"team": "India", "P": 2, "W": 1, "D": 1, "L": 0, "GF": 3, "GA": 2, "GD": 1, "Pts": 4},
    {"team": "Eng", "P": 2, "W": 1, "D": 1, "L": 0, "GF": 4, "GA": 1, "GD": 3, "Pts": 4},
    {"team": "Aus", "P": 2, "W": 0, "D": 0, "L": 2, "GF": 1, "GA": 5, "GD": -4, "Pts": 0}
]
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: customers**
| customer_id | name   |
|-------------|--------|
| 1           | Ravi   |
| 2           | Priya  |
| 3           | Karan  |
| 4           | Meena  |
| 5           | Arjun  |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 1           | 25000  | 2024-01-10 |
| 2        | 1           | 30000  | 2024-02-15 |
| 3        | 2           | 8000   | 2024-01-20 |
| 4        | 3           | 5000   | 2024-03-01 |
| 5        | 1           | 15000  | 2024-03-15 |

**Table: order_items**
| item_id | order_id | product_id | quantity |
|---------|----------|------------|----------|
| 1       | 1        | 1          | 1        |
| 2       | 2        | 1          | 1        |
| 3       | 3        | 2          | 3        |
| 4       | 4        | 2          | 1        |
| 5       | 5        | 1          | 2        |
(assume orders span multiple months for product 1)

**Problem 1:** Write a SQL query to find the top 3 customers by total spending amount.

**Problem 2:** Write a SQL query to find the total orders and total revenue per month from the `orders` table.

**Problem 3:** Write a SQL query to find products that have been ordered more than 3 times in total.

### Part D — OOP Based Problem

Design a content management system:
- `Content` base class with `content_id`, `title`, `author`, `created_at`, `status` (draft/published/archived)
- `Article(Content)` — has `body`, `tags` (list), `read_time`
- `Video(Content)` — has `url`, `duration`, `thumbnail`
- `Image(Content)` — has `url`, `alt_text`, `dimensions`
- `CMS` class with:
  - `add_content(content)`, `publish(content_id)`, `archive(content_id)`
  - `search(keyword)` — search across titles, bodies, tags
  - `filter_by_type(content_type)` — get only articles, videos, or images
  - `filter_by_status(status)`
  - `recent(n)` — last N published items
  - `stats()` — total content, breakdown by type, breakdown by status, most prolific author
- Demonstrate: add 4 articles, 3 videos, 2 images, publish some, archive some, show stats

### Part E — Django Based Problem

Build a DRF API for a Classroom Management System:
- Models: `Classroom` (name, grade, section, teacher_name, capacity) and `Student` (name, roll_number unique, classroom FK, parent_name, parent_phone, date_of_birth, is_active)
- Classroom serializer shows student count and available seats
- Student serializer shows classroom name
- ViewSets for both
- Custom actions:
  - `POST /classrooms/{id}/transfer-student/` — accepts student_id and target_classroom_id, handles capacity check
  - `GET /classrooms/{id}/attendance-summary/` — shows total, active, inactive students
  - `GET /students/birthdays/?month=1` — returns students with birthday in given month
- Filter students by classroom, is_active
- Search by student name, parent name
- Prevent exceeding classroom capacity when adding students
