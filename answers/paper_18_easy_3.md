# 📝 Question Paper 18 — Easy 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is a Python dictionary? How is it different from a list?
2. What is the `admin.py` file used for in Django?
3. What is the difference between `GROUP BY` and `ORDER BY` in SQL?
4. What are conditional statements in Python? Name the keywords used.
5. What is a URL parameter? Give an example.
6. What are data types in SQL? Name at least 5.
7. What is inheritance in OOP? Explain with a simple example.
8. What is `pip`? How do you install a specific version of a package?
9. What does the `startapp` command do in Django?
10. What is the difference between `==` and `!=` operators?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python method converts a string to uppercase?
2. What SQL function counts the number of rows?
3. What Django file handles the mapping between URLs and views?
4. What Python built-in function checks if all elements in a list are True?
5. What HTTP method is used to send data to create a new resource?
6. What method adds a key-value pair to a Python dictionary?
7. What SQL keyword is used to set a default value for a column?
8. What Python function gets input from the user?
9. What is the Django template syntax for displaying a variable?
10. What does `CSS` stand for?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of numbers and returns the second largest number.
```
Input:  [10, 5, 20, 8, 15]
Output: 15

Input:  [1, 1, 1]
Output: None (no second largest)
```

**Problem 2:** Write a function that converts a temperature from Celsius to Fahrenheit and vice versa based on a parameter.
```
Input:  convert(100, "C")  → 212.0 (Celsius to Fahrenheit)
Input:  convert(32, "F")   → 0.0   (Fahrenheit to Celsius)
```

**Problem 3:** Write a function that takes a list of tuples (name, score) and returns the names of students who scored above the average.
```
Input:  [("Ravi", 85), ("Priya", 60), ("Karan", 90), ("Meena", 55)]
Output: ["Ravi", "Karan"]  (average is 72.5)
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: users**
| user_id | fname      | last_name | email            |
|---------|------------|-----------|------------------|
| 1       | Ravi       | Kumar     | ravi@gmail.com   |
| 2       | Priya      | Sharma    | priya@yahoo.com  |
| 3       | Karan      | Singh     | karan@gmail.com  |

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 65000  |
| 2      | Priya  | HR         | 45000  |
| 3      | Karan  | Sales      | 50000  |
| 4      | Meena  | Finance    | 58000  |
| 5      | Arjun  | IT         | 72000  |

**Problem 1:** Write a SQL query to rename a column `fname` to `first_name` in the `users` table.

**Problem 2:** Write a SQL query to find employees who do NOT belong to the 'IT' or 'HR' department.

**Problem 3:** Write a SQL query to find the top 5 highest-paid employees.

### Part D — OOP Based Problem

Create a class `TodoList` with:
- An internal list to store tasks (each task is a dict with `title`, `done` status)
- Methods: `add_task(title)`, `complete_task(title)`, `pending_tasks()`, `completed_tasks()`
- `pending_tasks()` returns only incomplete tasks
- `completed_tasks()` returns only completed tasks
- Create a TodoList, add 5 tasks, complete 2, then display pending and completed

### Part E — Django Based Problem

Create a DRF API endpoint for a `Movie` model with fields: `title`, `genre`, `release_year`, `rating` (FloatField), `director`. Use `ModelSerializer` and `ModelViewSet`. Register the URLs using a router.
