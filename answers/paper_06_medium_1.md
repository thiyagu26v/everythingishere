# 📝 Question Paper 06 — Medium 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What are Python generators? How are they different from normal functions? 
generator are very usefull when we work with a iterables it uses the keyword yield which do work like a return but when we used return the loop may stopes their but when we yield it it return values one by one
2. Explain the Django request-response lifecycle. 
first the request get inside the middleware ..urls..views ..serializers....models...  again the same backwards
3. What is normalization in databases? Explain 1NF, 2NF, and 3NF briefly. i am not sure about those topics
4. What is the difference between shallow copy and deep copy in Python? shallow copy just create a copy but the actual object or reference is same ..when it deep copy it actually create a new object and save there
5. What are Django signals? Give a use case....signals are like a side effects of the primary action for example ...if i applied for a job on jobportal after i applied they can automatically sends the mail which successful applied ..they can did using signals
6. What is the difference between `@staticmethod` and `@classmethod`?  when we use staticmethod it dont need any self or cls as its first method , in class method its a second way without self we can use cls as its arguments
7. Explain DRF's `APIView` vs `ViewSet`. When would you choose one over the other? 
8. What are indexes in SQL? Why are they important?
9. What is the Global Interpreter Lock (GIL) in Python? (Just explain what it is in simple terms)
10. What is middleware in Django? Give an example of when you'd write custom middleware.  middleware is the most important in the request responce cycle ...when a request want to get in our app the middleware want to accept it likewise same for responce from the backend to client
---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What design pattern does Django follow?
2. What Python decorator makes a method behave like an attribute?
3. What SQL command is used to add a new column to an existing table?
4. What DRF permission class allows only authenticated users?
5. What HTTP status code means "Created"?
6. What Python library is commonly used for making HTTP requests?
7. What Django setting defines the list of allowed hostnames?
8. What SQL keyword is used to combine results of two SELECT queries?
9. What is the name of the Python package manager?
10. What method in DRF serializer is overridden to customize creation?

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of dictionaries (each with keys `name` and `score`) and returns the dictionary with the highest score.
```
Input:  [{"name": "Ravi", "score": 85}, {"name": "Priya", "score": 92}, {"name": "Karan", "score": 78}]
Output: {"name": "Priya", "score": 92}
```

**Problem 2:** Write a decorator function called `timer` that prints how long a function takes to execute.
```
# Usage:
@timer
def my_func():
    time.sleep(1)

my_func()
Output: "my_func took 1.001 seconds"
```

**Problem 3:** Write a function that groups a list of words by their first letter and returns a dictionary. Example: `["apple", "ant", "bat", "ball"]` → `{"a": ["apple", "ant"], "b": ["bat", "ball"]}`
```
Input:  ["apple", "ant", "bat", "ball", "cat"]
Output: {"a": ["apple", "ant"], "b": ["bat", "ball"], "c": ["cat"]}
```

**Problem 4:** Write a generator function that yields the Fibonacci sequence up to `n` numbers.
```
Input:  n = 7
Output: 0, 1, 1, 2, 3, 5, 8

    
```

### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name    | department | salary |
|--------|---------|------------|--------|
| 1      | Ravi    | IT         | 70000  |
| 2      | Priya   | IT         | 65000  |
| 3      | Karan   | HR         | 45000  |
| 4      | Meena   | IT         | 58000  |
| 5      | Arjun   | Sales      | 52000  |
| 6      | Divya   | HR         | 48000  |
| 7      | Suresh  | Sales      | 55000  |
| 8      | Anita   | IT         | 62000  |
| 9      | Raj     | HR         | 42000  |
| 10     | Pooja   | Sales      | 47000  |

**Problem 1:** Write a SQL query to find the top 3 highest-paid employees in each department.

**Problem 2:** Write a SQL query using a subquery to find employees who earn more than the average salary.

**Problem 3:** Write a SQL query to find departments that have more than 5 employees.

### Part D — OOP Based Problem

Create a class `Employee` with:
- Attributes: `name`, `department`, `salary`
- A class variable `employee_count` that tracks total employees created
- A class method `get_employee_count()` that returns the count
- A static method `is_valid_salary(salary)` that returns True if salary > 0
- Override `__repr__` to return a meaningful representation
- Create 3 employee objects and demonstrate all methods

### Part E — Django Based Problem

Build a DRF API endpoint for a `Note` model (fields: `title`, `body`, `created_at`, `updated_at`). Create the model, serializer, viewset, and URL configuration. The API should support full CRUD operations. Add a filter so users can search notes by title.
