# 📝 Question Paper 29 — Advanced 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the `@property` decorator in Python? How do you create getter, setter, and deleter?
2. What are Django's generic views? Name 5 commonly used ones.
3. What is the difference between `GROUP BY` and `ORDER BY` in SQL?
4. What is multiple inheritance in Python? Give an example.
5. How does DRF handle content negotiation? What does `Accept` header do?
6. What are `collections.Counter` and `collections.namedtuple`? Give examples.
7. What is the difference between `UNION` and `JOIN` in SQL?
8. What is Django's `annotate()` vs `aggregate()`? Give examples of each.
9. What is the Global Interpreter Lock (GIL) in Python? (Just explain what it is in simple terms)
10. What is the difference between authentication and authorization in web security?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function creates a frozen (immutable) set?
2. What SQL function counts only non-NULL values?
3. What DRF decorator marks a ViewSet method as a custom action?
4. What Python method joins list elements into a string?
5. What HTTP status code means "Conflict"?
6. What built-in function returns the largest item in an iterable?
7. What SQL keyword ensures no duplicate rows in results?
8. What Django field auto-sets the date when an object is first created?
9. What Python keyword creates an anonymous function?
10. What does `CDN` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a student's course schedule (list of course dicts with name, day, start_time, end_time) and detects any scheduling conflicts.
```
Input:  [
    {"course": "Math", "day": "Mon", "start": "09:00", "end": "10:30"},
    {"course": "Physics", "day": "Mon", "start": "10:00", "end": "11:30"},
    {"course": "Chemistry", "day": "Tue", "start": "09:00", "end": "10:00"}
]
Output: [{"conflict": ["Math", "Physics"], "day": "Mon", "overlap": "10:00-10:30"}]
```

**Problem 2:** Write a function that takes a nested dictionary and flattens it using dot notation as keys.
```
Input:  {"a": 1, "b": {"c": 2, "d": {"e": 3}}, "f": 4}
Output: {"a": 1, "b.c": 2, "b.d.e": 3, "f": 4}
```

**Problem 3:** Write a function that generates a password based on rules: length, include uppercase, include numbers, include special characters. Return the generated password.
```
Input:  length=12, uppercase=True, numbers=True, special=True
Output: "aK3$mN8pQ#1x" (random but meeting all criteria)
```

**Problem 4:** Write a function that takes a list of dictionaries representing employees with `name`, `department`, `salary` and returns a department-wise summary: total salary, average salary, highest paid, and employee count.
```
Input:  [
    {"name": "Ravi", "dept": "IT", "salary": 60000},
    {"name": "Priya", "dept": "IT", "salary": 75000},
    {"name": "Karan", "dept": "HR", "salary": 50000}
]
Output: {
    "IT": {"total": 135000, "avg": 67500, "highest_paid": "Priya", "count": 2},
    "HR": {"total": 50000, "avg": 50000, "highest_paid": "Karan", "count": 1}
}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: customers**
| customer_id | name   |
|-------------|--------|
| 1           | Ravi   |
| 2           | Priya  |
| 3           | Karan  |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 1           | 5000   | 2024-01-10 |
| 2        | 1           | 3000   | 2024-02-15 |
| 3        | 1           | 7000   | 2024-03-01 |
| 4        | 2           | 2000   | 2024-04-20 |
| 5        | 3           | 4500   | 2024-05-10 |
| ...      | ...         | ...    | ...        |
(assume orders span all 12 months for customer 1)

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 60000  |
| 2      | Priya  | IT         | 60000  |
| 3      | Karan  | HR         | 50000  |
| 4      | Meena  | HR         | 50000  |
| 5      | Arjun  | Sales      | 55000  |

**Table: product_sales**
| sale_id | product_id | product_name | amount |
|---------|------------|--------------|--------|
| 1       | 101        | Laptop       | 50000  |
| 2       | 102        | Mouse        | 500    |
| 3       | 101        | Laptop       | 50000  |
| 4       | 103        | Keyboard     | 1500   |

**Problem 1:** Write a SQL query to find customers who have placed more than 3 orders.

**Problem 2:** Write a SQL query using a self-join to find employees who share the same department and have the same salary.

**Problem 3:** Write a SQL query to find each product's name and its contribution as a percentage of total sales.

### Part D — OOP Based Problem

Design a library management system:
- `Book` class with `isbn`, `title`, `author`, `copies_total`, `copies_available`
- `Member` class with `member_id`, `name`, `borrowed_books` (list)
- `Library` class with:
  - `add_book(book)`, `add_member(member)`
  - `borrow_book(member_id, isbn)` — reduce availability, add to member's list
  - `return_book(member_id, isbn)` — increase availability, remove from member's list
  - `search_book(title or author)` — partial match search
  - `overdue_report()` — if you add due dates
  - `popular_books()` — books with most borrows
- Handle: borrowing unavailable book, member borrowing limit (max 3)
- Demonstrate full flow

### Part E — Django Based Problem

Build a DRF API for a Survey System:
- Models: `Survey` (title, description, is_active, created_at) and `Question` (survey FK, text, question_type choices: text/single_choice/multiple_choice) and `Response` (question FK, respondent_name, answer, submitted_at)
- Survey serializer shows questions nested
- ViewSets for Survey, Question, Response
- Custom action on Survey: `GET /surveys/{id}/results/` — returns answer summary per question
- Only active surveys shown in listing
- Filter by question_type
