# 📝 Question Paper 04 — Easy 4

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `args` and `kwargs` in Python? 
both are used when  we dont know the actual number of argumensts we pass into the funtion , so we use args for more no of argumensts and kwargs for mor no of keyword arguments
2. What is a migration in Django? Why is it important?
migration in django was updating the django model into the actual database ..the most importan commands are make migration for take the history copy and migrate command used for updated the models into actual table
3. What is the difference between `WHERE` and `HAVING` in SQL? 
where used when we give condition to the rows 
having used when we used any aggregate function or did groupby
4. What are Python's built-in data structures? Name all of them.
i cant understand the question but i answer what i understand builtin data structures in python are list , tuple, dict, set
5. What is the Django admin panel? How do you register a model?
django admin panel is used for having supiorior of the whole project , using admin we can control whole model or a data table 
6. What is exception handling in Python? Name the keywords used.
exception handling is a important cocept in python exception is actualy handelig error . the key word used is except ...for example if we know the input given from the user  may invalid itmay occur error ...so we        write those code inside the       try and we can raise erroron except
7. What is the difference between `views.py` function-based views and class-based views?     function  based views are very basic only for simple logics ....there class based views used in most of the complex codebase to simply it have more inbuilt features we dont want to write all logics manually
8. What is a queryset in Django?   query sets are the objects that contains all the datasets
9. What is the difference between `DELETE` and `TRUNCATE` in SQL?
10. What is `pip freeze` and why is it useful?

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python built-in function returns a sorted version of a list? .sorted()
2. What SQL keyword is used to combine rows from two tables? 
3. What is the default database used by Django? sqlite
4. What Python method splits a string into a list? .split()
5. What does `JSON` stand for?  javascript object notation
6. What command creates a new app inside a Django project? python startapp appname
7. What operator is used for floor division in Python? 
8. What SQL function returns the total sum of a numeric column? sum()
9. What HTTP status code means "Not Found"? 404
10. What Python module is used for working with dates and times? dateandtime

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that accepts a list of words and returns the longest word.
```
Input:  ["cat", "elephant", "dog", "tiger"]
Output: "elephant"
 words = ["cat", "elephant", "dog", "tiger"]

def long(words):
    counts=0
    for i in words:
        if len(i)> counts:
            counts = len(i)
    
    for i in words :
        if len(i) == counts:
            return (i) 
        
print(long(words))





`

**Problem 2:** Write a program that creates a dictionary from two lists — one of keys and one of values.
```
Input:  keys = ["name", "age", "city"], values = ["Ravi", 25, "Chennai"]
Output: {"name": "Ravi", "age": 25, "city": "Chennai"}
```

for i in keys:
    

**Problem 3:** Write a function that takes a sentence and returns the number of words in it.
```
Input:  "Hello world this is Python"
Output: 5
```
def count(arr):
    splited = arr.split()
    count = 0
    for i in splited:
        count +=1
    return count


### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name    | department | salary |
|--------|---------|------------|--------|
| 1      | Arjun   | IT         | 55000  |
| 2      | Anita   | HR         | 40000  |
| 3      | Ravi    | IT         | 48000  |
| 4      | Priya   | Sales      | 42000  |
| 5      | Arun    | Sales      | 38000  |
| 6      | Karan   | HR         | 45000  |

**Problem 1:** Write a SQL query to find the highest salary in the `employees` table.

select max(e.salary)
from employees e

**Problem 2:** Write a SQL query to find all employees whose name starts with the letter 'A'.
select * 
from employees e
where e.name like %A

**Problem 3:** Write a SQL query to count employees in each department using `GROUP BY`.
select e.department , count(e.name )  as employees_in_depart
from employees e
group by e.department


### Part D — OOP Based Problem

Create a class `Car` with:
- Attributes: `brand`, `model`, `year`, `is_running` (default False)
- Methods: `start()`, `stop()`, `display_status()`
- `start()` sets `is_running` to True, `stop()` sets it to False
- Create a car object, start it, display status, stop it, display status again
class car():
    def __init__(self,brand,model,year,is_running = False):
        self.brand = brand 
        self.model = model
        self.year = year
        self.is_running = is_running 
    
    def start(self):
        self.is_running = True
        return "car started"
    def stop(self):
        self.is_running = False
        return "car stoped"
            
            
    def display_status(self):
        return (f"brand name : {self.brand} \n model: {self.model} \n year :{self.year} \n status running :{self.is_running}")
    
    
car1 = car("benz","m5",2012)

print(car1.start())
print(car1.display_status())
print(car1.stop())
print(car1.display_status())


### Part E — Django Based Problem

Create a simple DRF serializer for a `Product` model that has fields: `id`, `name`, `price`, `description`. Write the serializer class in `serializers.py`.


serializers.py

class productSerializer(seriaizers.serializer):
    id = serializers.integerfield(auto_increment_add)
    name = serializers. charField(max_length = 30)
    price = serializers.integerField()
    description = serializers.textField(max_length = 300)
    

