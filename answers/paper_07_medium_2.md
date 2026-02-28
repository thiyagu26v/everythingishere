# 📝 Question Paper 07 — Medium 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `__str__` and `__repr__` in Python?
2. Explain how Django handles database relationships (OneToOne, ForeignKey, ManyToMany).
3. What is a transaction in SQL? Explain ACID properties.
4. What is the difference between `map()`, `filter()`, and `reduce()` in Python?
5. What is pagination in DRF? What are the different pagination styles?
6. What are Python context managers? Explain the `with` statement.
7. What is Django's `select_related()`? How does it help with database queries?
8. What is the difference between `UNION` and `UNION ALL` in SQL?
9. What are Python magic/dunder methods? Name at least 5.
10. Explain the difference between synchronous and asynchronous processing.

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Django method prefetches related objects to avoid N+1 queries?
2. What Python data structure provides O(1) average lookup time?
3. What SQL clause is used with aggregate functions to filter groups?
4. What DRF class converts model instances to JSON and vice versa?
5. What HTTP status code means "Unauthorized"?
6. What Python keyword is used with generators to produce values?
7. What Django command creates migration files?
8. What SQL keyword creates a virtual table based on a query?
9. What is the name of Django's built-in user authentication model?
10. What Python built-in function creates an iterator of tuples from two lists?

### Part B — Python Live Coding Problems

**Problem 1:** Write a class `SimpleCache` that stores key-value pairs with a maximum size. When adding a new item and the cache is full, remove the oldest item added.
```
cache = SimpleCache(max_size=3)
cache.put("a", 1)
cache.put("b", 2)
cache.put("c", 3)
cache.get("a")       → 1
cache.put("d", 4)    → removes "a" (first added)
cache.get("a")       → -1 (not found)
```

**Problem 2:** Write a function that reads a file and counts the frequency of each word.
```
# If file "test.txt" contains: "hello world hello python world hello"
Input:  count_words("test.txt")
Output: {"hello": 3, "world": 2, "python": 1}
```

**Problem 3:** Write a function that takes a nested dictionary and flattens it. Example: `{"a": {"b": 1, "c": {"d": 2}}}` → `{"a.b": 1, "a.c.d": 2}`
```
Input:  {"user": {"name": "Ravi", "address": {"city": "Chennai", "pin": 600001}}}
Output: {"user.name": "Ravi", "user.address.city": "Chennai", "user.address.pin": 600001}
```

**Problem 4:** Write a function that validates an email address using regex. It should check for a valid format (basic validation).
```
Input:  "ravi@example.com"   → True
Input:  "ravi@.com"          → False
Input:  "hello@world"        → False
Input:  "test@mail.co.in"    → True
```

### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name    | department | salary |
|--------|---------|------------|--------|
| 1      | Ravi    | IT         | 50000  |
| 2      | Priya   | HR         | 50000  |
| 3      | Karan   | IT         | 65000  |
| 4      | Meena   | Sales      | 45000  |
| 5      | Arjun   | HR         | 55000  |
| 6      | Divya   | IT         | 72000  |

**Problem 1:** Write a SQL query to find employees who have the same salary (use self-join).

**Problem 2:** Write a SQL query to find the total salary for each department and order by highest total first.

**Problem 3:** Create a SQL view called `high_earners` that shows employees with salaries above 50000.

### Part D — OOP Based Problem

Design a simple library system with:
- A `Book` class with attributes: `title`, `author`, `isbn`, `is_available`
- A `Library` class that:
  - Has a list of books
  - Can `add_book(book)`, `remove_book(isbn)`, `find_book(title)`, `list_available_books()`
- A `Member` class that can `borrow_book(book)` and `return_book(book)`
- Demonstrate the interaction between these classes

### Part E — Django Based Problem

Create a DRF API with two related models: `Author` (name, email) and `Book` (title, author as ForeignKey, published_date, price). Create serializers with nested representation — when fetching a book, the author details should be included. Implement `ListCreateAPIView` and `RetrieveUpdateDestroyAPIView` for both models.
