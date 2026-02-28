# 📝 Question Paper 14 — Advanced 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. How does Python's import system work? What is the difference between `import` and `from ... import`?
2. How would you implement soft delete in Django? What does it mean?
3. What is the difference between `DELETE`, `TRUNCATE`, and `DROP` in SQL?
4. What is multiple inheritance in Python? What problems can it cause?
5. What is the difference between `ModelSerializer` and `Serializer` in DRF? When would you use which?
6. How do you handle file reading and writing in Python? Explain different modes (`r`, `w`, `a`, `rb`).
7. How do you optimize slow Django queries? What tools would you use?
8. What is the difference between a `list` and a `set` in Python?
9. What is the difference between a development server and a production server?
10. What is middleware in Django? How would you write a custom one?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python function converts a string to an integer?
2. What SQL feature lets you define a variable that holds a single value for use in queries?
3. What DRF decorator is used to mark a viewset method as a custom action?
4. What Python module helps with file operations like creating/deleting directories?
5. What Django middleware class handles clickjacking protection?
6. What HTTP method returns only headers without a response body?
7. What SQL technique converts column values into row values?
8. What Python typing feature allows you to define type aliases and unions?
9. What DRF exception class returns a 400 response with validation details?
10. What is the MVC/MVT pattern? Which one does Django use?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of orders (each with `items`, `quantities`, `prices`) and generates an invoice: line items with subtotals, overall total, tax (18% GST), discount (10% if total > 5000), and final amount.
```
Input:  [
    {"item": "Laptop", "qty": 1, "price": 50000},
    {"item": "Mouse", "qty": 2, "price": 500}
]
Output: {
    "line_items": [
        {"item": "Laptop", "qty": 1, "price": 50000, "subtotal": 50000},
        {"item": "Mouse", "qty": 2, "price": 500, "subtotal": 1000}
    ],
    "total": 51000,
    "discount": 5100,
    "tax": 8262,
    "final_amount": 54162
}
```

**Problem 2:** Write a class `PasswordValidator` that checks multiple rules: minimum length, at least one uppercase, one lowercase, one digit, one special character, no spaces, and not in a list of common passwords. Return all failed rules.
```
Input:  "hello"
Output: {"valid": False, "errors": ["Min 8 characters", "Need uppercase", "Need digit", "Need special char"]}

Input:  "Ravi@2025"
Output: {"valid": True, "errors": []}
```

**Problem 3:** Write a function that takes a list of file paths and organizes them into a nested dictionary representing the folder structure.
```
Input:  [
    "src/app/main.py",
    "src/app/utils.py",
    "src/tests/test_main.py",
    "README.md"
]
Output: {
    "src": {
        "app": {"main.py": None, "utils.py": None},
        "tests": {"test_main.py": None}
    },
    "README.md": None
}
```

**Problem 4:** Write a function that takes a text paragraph and returns statistics: word count, sentence count, most common word, average word length, and reading time (assuming 200 words per minute).
```
Input:  "Python is great. Python is easy to learn. I love Python programming."
Output: {
    "word_count": 12,
    "sentence_count": 3,
    "most_common_word": "Python",
    "avg_word_length": 4.5,
    "reading_time_seconds": 3.6
}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: friendships**
| user_id | friend_id |
|---------|-----------|
| 1       | 2         |
| 1       | 3         |
| 2       | 3         |
| 2       | 4         |
| 3       | 4         |
| 3       | 5         |

**Table: product_prices**
| product_id | category    | price | recorded_date |
|------------|-------------|-------|---------------|
| 1          | Electronics | 50000 | 2024-01-01    |
| 1          | Electronics | 48000 | 2024-02-01    |
| 1          | Electronics | 20000 | 2024-03-01    |
| 2          | Clothing    | 2000  | 2024-01-01    |
| 2          | Clothing    | 2100  | 2024-02-01    |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 101         | 5000   | 2024-01-10 |
| 2        | 101         | 3000   | 2024-01-15 |
| 3        | 101         | 7000   | 2024-02-01 |
| 4        | 102         | 2000   | 2024-01-20 |
| 5        | 102         | 8000   | 2024-02-10 |

**Problem 1:** Write a SQL query to find the user with the most friends from the `friendships` table (count appearances in both `user_id` and `friend_id` columns).

**Problem 2:** Write a SQL query to find the most frequently recorded price for each product from the `product_prices` table.

**Problem 3:** Write a SQL query to find each customer's most recent order (showing customer_id, amount, and order_date).

### Part D — OOP Based Problem

Design a simple order tracking system:
- `Order` class with `order_id`, `customer_name`, `items` (list), `total_amount`, `status` (pending/confirmed/shipped/delivered/cancelled)
- `OrderManager` class:
  - `create_order(customer, items)` — create a new order with 'pending' status
  - `confirm_order(order_id)` — change to 'confirmed'
  - `ship_order(order_id)` — change to 'shipped'
  - `deliver_order(order_id)` — change to 'delivered'
  - `cancel_order(order_id)` — cancel if not already shipped/delivered
  - `get_orders_by_status(status)` — filter orders
  - `order_history(order_id)` — show status change history
- Handle: cancelling shipped orders, updating non-existent orders
- Demonstrate with 4 orders going through different paths

### Part E — Django Based Problem

Build a Chat/Messaging API:
- Models:
  - `Conversation` (participants M2M User, created_at, updated_at)
  - `Message` (conversation FK, sender FK User, content, message_type choices: text/image/file, is_read, created_at)
- Endpoints:
  - `GET /conversations/` — list user's conversations with last message preview
  - `POST /conversations/` — create conversation with participants
  - `GET /conversations/{id}/messages/` — paginated messages (cursor-based pagination)
  - `POST /conversations/{id}/messages/` — send a message
  - `POST /conversations/{id}/read/` — mark all messages as read
- Custom annotations: unread count per conversation
- Only conversation participants can access the conversation
- Order conversations by most recent message
- Efficient queries: avoid N+1 in conversation listing
