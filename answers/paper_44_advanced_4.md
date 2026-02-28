# 📝 Question Paper 44 — Advanced 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the `@property` decorator in Python? Give a simple example.
2. What is Django's `bulk_create()` and `bulk_update()`? When would you use them?
3. What is the difference between a `VIEW` and a regular `TABLE` in SQL?
4. What is the `enum` module in Python? When do you use it instead of string constants?
5. What are DRF's `ListSerializer` and `many=True`? How do they work?
6. What is the `logging` module in Python? Compare it with using `print()` statements.
7. What is a SQL execution plan at a basic level? Why is query performance important?
8. What is the difference between `defer()` and `only()` in Django ORM?
9. What is the `typing` module in Python? What are type hints and why use them?
10. What is a webhook callback? How does it differ from request-response APIs?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method checks if a string starts with a specific character?
2. What SQL function returns the number of distinct values?
3. What DRF throttle class limits requests per user?
4. What Python built-in function converts a character to its ASCII value?
5. What HTTP status code means "Payload Too Large"?
6. What built-in function returns a property attribute?
7. What SQL clause specifies the number of rows to skip?
8. What Django method chains multiple filter conditions?
9. What Python exception is raised when dividing by zero?
10. What does `CORS` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of restaurant orders (table_number, items with names and prices, tip_percentage) and generates an end-of-day report: total revenue, total tips, average bill, busiest table, and item sales count.
```
Input:  [
    {"table": 1, "items": [{"name": "Burger", "price": 250}, {"name": "Coke", "price": 80}], "tip": 10},
    {"table": 2, "items": [{"name": "Pizza", "price": 400}, {"name": "Burger", "price": 250}], "tip": 15},
    {"table": 1, "items": [{"name": "Pasta", "price": 300}], "tip": 10}
]
Output: {
    "total_revenue": 1280,
    "total_tips": 160.5,
    "avg_bill": 426.67,
    "busiest_table": 1,
    "item_counts": {"Burger": 2, "Coke": 1, "Pizza": 1, "Pasta": 1}
}
```

**Problem 2:** Write a function that validates an Indian PAN card number. Rules: 5 uppercase letters, 4 digits, 1 uppercase letter. The 4th character must be 'P' for individuals.
```
Input:  "ABCPD1234E"
Output: {"valid": True, "type": "Individual"}

Input:  "ABCCD1234E"
Output: {"valid": True, "type": "Company"}

Input:  "ABC1D1234E"
Output: {"valid": False, "reason": "First 5 characters must be letters"}
```

**Problem 3:** Write a function that takes a list of tasks with priorities (high, medium, low) and sorts them by priority order.
```
Input:  [{"task": "Fix bug", "priority": "high"}, {"task": "Write docs", "priority": "low"}, {"task": "Code review", "priority": "medium"}, {"task": "Deploy", "priority": "high"}]
Output: [{"task": "Fix bug", "priority": "high"}, {"task": "Deploy", "priority": "high"}, {"task": "Code review", "priority": "medium"}, {"task": "Write docs", "priority": "low"}]
```

**Problem 4:** Write a function that takes a time series of temperature readings (datetime, temp) and finds: hottest day, coldest day, average temperature, days above 35°C, and trend (warming/cooling/stable).
```
Input:  [
    {"date": "2025-05-01", "temp": 32},
    {"date": "2025-05-02", "temp": 34},
    {"date": "2025-05-03", "temp": 36},
    {"date": "2025-05-04", "temp": 38},
    {"date": "2025-05-05", "temp": 37}
]
Output: {"hottest": "2025-05-04", "coldest": "2025-05-01", "avg": 35.4, "above_35": 3, "trend": "warming"}
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: products**
| product_id | name     | category    |
|------------|----------|-------------|
| 1          | Laptop   | Electronics |
| 2          | Mouse    | Electronics |
| 3          | Keyboard | Electronics |
| 4          | Notebook | Stationery  |

**Table: order_items**
| item_id | order_id | product_id | quantity |
|---------|----------|------------|----------|
| 1       | 1        | 1          | 5        |
| 2       | 2        | 2          | 10       |
| 3       | 3        | 3          | 3        |
| 4       | 4        | 1          | 2        |

**Table: sales**
| sale_id | amount | sale_date  |
|---------|--------|------------|
| 1       | 5000   | 2024-01-10 |
| 2       | 3000   | 2024-01-11 |
| 3       | 7000   | 2024-01-12 |
| 4       | 4000   | 2024-01-13 |

**Table: orders**
| order_id | customer_id | amount | order_date |
|----------|-------------|--------|------------|
| 1        | 101         | 5000   | 2024-01-10 |
| 2        | 101         | 3000   | 2024-02-15 |
| 3        | 102         | 7000   | 2024-01-20 |
| 4        | 101         | 2000   | 2024-03-05 |

**Problem 1:** Write a SQL query to find the top-selling product in each category by total quantity sold.

**Problem 2:** Write a SQL query to find the total quantity sold for each product.

**Problem 3:** Write a SQL query to show a customer's order history with a running total column.

### Part D — OOP Based Problem

Design an airline booking system:
- `Flight` class with `flight_number`, `origin`, `destination`, `departure_time`, `seats_total`, `seats_booked`, `price`
- `Passenger` class with `passenger_id`, `name`, `email`, `bookings` (list)
- `BookingSystem` class with:
  - `add_flight(flight)`, `register_passenger(passenger)`
  - `search_flights(origin, destination, date)` — find available flights
  - `book_ticket(passenger_id, flight_number)` — book if seats available, return booking_id
  - `cancel_ticket(booking_id)` — cancel and free seat
  - `check_in(booking_id)` — mark as checked in
  - `flight_manifest(flight_number)` — list all passengers on a flight
  - `revenue_report()` — total revenue, flights by capacity utilization
- Handle: overbooking, duplicate bookings, cancelling checked-in tickets
- Demonstrate with 4 flights and 6 passengers

### Part E — Django Based Problem

Build a DRF API for a Fitness Tracker:
- Models: `Exercise` (name, category choices: cardio/strength/flexibility/sports, calories_per_minute) and `Workout` (user_name, exercise FK, duration_minutes, date, notes TextField nullable)
- Exercise serializer shows total workout count
- Workout serializer shows exercise name and calories burned
- ViewSets for both
- Custom actions:
  - `GET /workouts/summary/?user=Ravi&month=2025-01` — returns total workouts, total duration, total calories, most frequent exercise, days active
  - `GET /workouts/streaks/?user=Ravi` — returns current streak and longest streak of consecutive workout days
- Filter workouts by user_name, exercise, date range
- Ordering by date, duration
