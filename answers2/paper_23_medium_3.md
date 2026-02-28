# 📝 Question Paper 23 — Medium 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `map()`, `filter()`, and `reduce()` in Python?
2. What is Django's `QuerySet`? How is it lazy?
3. What is the difference between `HAVING` and `WHERE` when used with `GROUP BY`?
4. What is the difference between a list and a dictionary in Python?
5. What are DRF throttling classes? How do you configure rate limiting?
6. What are default function arguments in Python? Give an example.
7. What is an SQL index? What are the advantages and disadvantages?
8. What is the difference between `render()` and `JsonResponse()` in Django?
9. What is the difference between synchronous and asynchronous programming?
10. What is `super()` in Python? How does it work with inheritance?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function returns a reversed iterator?
2. What SQL keyword creates an index on a table?
3. What DRF class handles object-level permissions?
4. What Python method removes and returns the last element of a list?
5. What HTTP status code means "No Content"?
6. What built-in function zips two lists together?
7. What SQL keyword is used to check if a value exists in a list?
8. What Django method excludes specific records from a queryset?
9. What Python module is used to work with JSON data?
10. What does `DRY` stand for in software development?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a nested list of varying depths and returns a flat list.
```
Input:  [1, [2, 3], [4, [5, 6]], 7, [[8]]]
Output: [1, 2, 3, 4, 5, 6, 7, 8]
```

**Problem 2:** Write a function that takes a list of strings and finds the longest common prefix.
```
Input:  ["interview", "internal", "internet"]
Output: "inter"

Input:  ["dog", "cat", "bird"]
Output: ""
```

**Problem 3:** Write a function that rotates a list by `k` positions to the right.
```
Input:  [1, 2, 3, 4, 5], k = 2
Output: [4, 5, 1, 2, 3]
```

**Problem 4:** Write a function that takes a list of timestamps (strings) and returns the time difference between the earliest and latest.
```
Input:  ["09:15:00", "14:30:00", "23:45:00", "06:00:00"]
Output: "17 hours 45 minutes"
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary | is_active |
|--------|--------|------------|--------|-----------|
| 1      | Ravi   | IT         | 65000  | true      |
| 2      | Priya  | HR         | 48000  | true      |
| 3      | Karan  | IT         | 55000  | false     |
| 4      | Meena  | Sales      | 72000  | true      |
| 5      | Arjun  | HR         | 60000  | true      |

**Table: products**
| product_id | name     | price | category    |
|------------|----------|-------|-------------|
| 1          | Laptop   | 50000 | Electronics |
| 2          | Mouse    | 500   | Electronics |
| 3          | Notebook | 100   | Stationery  |
| 4          | Headset  | 2000  | Electronics |

**Table: order_items**
| item_id | order_id | product_id | quantity |
|---------|----------|------------|----------|
| 1       | 1        | 1          | 1        |
| 2       | 2        | 2          | 3        |

**Problem 1:** Write a SQL query to find employees whose salary is above the average salary of the entire company.

**Problem 2:** Write a SQL query to find all products that have never been ordered (use a LEFT JOIN with the `order_items` table).

**Problem 3:** Write a SQL query to create a view called `active_employees` that shows employees where `is_active` is true, displaying their name, department, and salary.

### Part D — OOP Based Problem

Design a simple ticket booking system:
- `Ticket` class with `ticket_id`, `event_name`, `seat_number`, `price`, `is_booked` (default False)
- `BookingSystem` class with:
  - `available_tickets()` — returns list of unbooked tickets
  - `book_ticket(ticket_id, customer_name)` — books a ticket, raises error if already booked
  - `cancel_booking(ticket_id)` — cancels a booking
  - `revenue()` — returns total revenue from booked tickets
  - `bookings_summary()` — returns dict with total tickets, booked, available, revenue
- Create 10 tickets, book 4, cancel 1, show summary

### Part E — Django Based Problem

Build a DRF API for an Expense Tracker:
- Model: `Expense` with fields: `title`, `amount` (DecimalField), `category` (choices: food, transport, shopping, bills, entertainment, other), `date`, `description`, `created_by` (CharField)
- ViewSet with full CRUD
- Filter by category and date range
- Add an endpoint that returns total expenses grouped by category

---

## SECTION 3: PREDICT THE OUTPUT

### List Comprehension

**Q1 (MCQ):** What is the output?
```python
result = [x for x in "HeLLo" if x == x.upper()]
print(result)
```
a) `["H", "e", "L", "L", "o"]`
b) `["H", "L", "L"]`
c) `["e", "o"]`
d) `["HELLO"]`

**Q2 (MCQ):** What is the output?
```python
nums = [10, 20, 30]
result = [x // 3 for x in nums]
print(result)
```
a) `[3.33, 6.67, 10.0]`
b) `[3, 6, 10]`
c) `[1, 2, 0]`
d) `[10, 20, 30]`

**Q3 (MCQ):** What is the output?
```python
a = [1, 2, 3]
b = [4, 5, 6]
result = [x * y for x, y in zip(a, b)]
print(result)
```
a) `[5, 7, 9]`
b) `[4, 10, 18]`
c) `[(1, 4), (2, 5), (3, 6)]`
d) `[1, 2, 3, 4, 5, 6]`

**Q4 (Open-Ended):** What is the output?
```python
sentence = "python is great"
result = [word.capitalize() for word in sentence.split()]
print(" ".join(result))
```

**Q5 (Open-Ended):** What is the output?
```python
nums = [1, 2, 3, 4, 5]
result = [nums[-(i+1)] for i in range(len(nums))]
print(result)
```

### Lambda Functions

**Q6 (MCQ):** What is the output?
```python
classify = lambda n: "positive" if n > 0 else "negative" if n < 0 else "zero"
results = [classify(x) for x in [5, -3, 0]]
print(results)
```
a) `[5, -3, 0]`
b) `["positive", "negative", "zero"]`
c) `["true", "true", "false"]`
d) `Error`

**Q7 (MCQ):** What is the output?
```python
names = ["ravi", "PRIYA", "Karan"]
result = list(map(lambda n: n.capitalize(), names))
print(result)
```
a) `["ravi", "PRIYA", "Karan"]`
b) `["Ravi", "Priya", "Karan"]`
c) `["RAVI", "PRIYA", "KARAN"]`
d) `["R", "P", "K"]`

**Q8 (MCQ):** What is the output?
```python
nums = [10, 25, 30, 45, 50, 65]
result = list(filter(lambda x: x % 10 == 0, nums))
print(result)
```
a) `[25, 45, 65]`
b) `[10, 30, 50]`
c) `[10, 25, 30, 45, 50, 65]`
d) `[]`

**Q9 (Open-Ended):** What is the output?
```python
join_with = lambda sep, *args: sep.join(args)
print(join_with("-", "2024", "01", "15"))
```

**Q10 (Open-Ended):** What is the output?
```python
transform = lambda lst, fn: [fn(x) for x in lst]
result = transform([1, 2, 3, 4], lambda x: x ** 2 + 1)
print(result)
```
