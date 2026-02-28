# 📝 Question Paper 05 — Easy 5

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between `break`, `continue`, and `pass` in Python?
break will instantly break the loop ...continue used when we want to complete the full work without error raised ...pass is just like a filler 
2. What is the purpose of `serializers.py` in DRF?
serializers.py in django is used to validate the responce from the post request and give the valid data back ,it converts objects into json format
3. What are aggregate functions in SQL? Name at least 3.
aggretage function used when we did a groupby ..sum(),averagea() m max()
4. What is a lambda function in Python?  lambda function is a special function used to write one line logics
5. Explain the MVC/MVT architecture. How does Django follow it?   django follows mvt architecture not mvc but similar to mvc....because djangos base structure was models ,views, templates , and urls in mvt m refers to models  on models each class refers to the database tabel   v refers to views where actually we connect every files and write our business logics and t refers to the template what users see basically its a html
6. What is the difference between `INNER JOIN` and `LEFT JOIN`?  inner join in sql returns data sets from both table which acts like union of table ...left join shows all rows and coloums from left table and show the datas from right table ..it allows null on the left table
7. What is `self` in Python? Why is it used in class methods?  self refers to the current class which helps to pass argumenst from class level to all methods level ..for example if we declared a class level variable inside class we can use on any metthod on the class using self like self.variable name ..which is also handled by the child classes also 
8. What is the difference between authentication and authorization?authentication looks who is want to login or who is this and authorization refers to what he can do or what are the powers it has 
9. What is a Python module vs a Python package?  a single files with a .py extention is a module and a folder with various py.files with init.py file is package for exampple installed  libraries
10. What are Django templates? What is the template engine? 
im not sure about template engine django templates are the frontend of our projecrs which contains what the users can see in the browser basically it wasma html file

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python keyword is used to exit a loop early? break
2. What SQL keyword is used to create a new table? create
3. What DRF class is used to create API views easily? API view
4. What Python function opens a file for reading or writing? open()  read()
5. What Django template tag is used for loops? 
6. What is the default content type for a DRF response? json
7. What Python method joins list elements into a string? " ".join()
8. What SQL constraint ensures all values in a column are unique? unique
9. What does `WSGI` stand for? im not sure but this file is used on deployment
10. What Python keyword is used for inheritance? its not about keyword its about the logic

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a number `n` and returns the factorial of `n` using a loop (not recursion).
```
Input:  5
Output: 120

Input:  0
Output: 1
```
def factorial(n):
    result = 1
    for i in range (1,n+1):
        result =  result * i
        print (result)

**Problem 2:** Write a program that takes a list of numbers and separates them into two lists: one for odd numbers and one for even numbers.
```
Input:  [1, 2, 3, 4, 5, 6, 7, 8]
Output: odd = [1, 3, 5, 7], even = [2, 4, 6, 8]

def odd_even(arr1):
    odd=[]
    even=[]
    for i in arr1:
        if i % 2 == 0:
            even.append(i)
        else:
            odd.append(i)
            
    return (f"odd:{odd} even: {even}")
    
```

**Problem 3:** Write a function that flattens a nested list. Example: `[[1,2],[3,[4,5]]]` → `[1,2,3,4,5]`
```
Input:  [[1, 2], [3, [4, 5]]]
Output: [1, 2, 3, 4, 5]

def flatten(listtt):
    result = []
    for i in listtt:
        if i .isdigit():
            result.append(i)
    return result
```

### Part C — SQL Live Problems

**Use these tables for the problems:**

**Table: employees**
| emp_id | name   | department | salary | hire_date  |
|--------|--------|------------|--------|------------|
| 1      | Ravi   | IT         | 60000  | 2023-04-10 |
| 2      | Priya  | HR         | 55000  | 2024-01-15 |
| 3      | Karan  | IT         | 60000  | 2024-07-20 |
| 4      | Meena  | Sales      | 48000  | 2022-09-05 |
| 5      | Arjun  | Finance    | 52000  | 2024-11-12 |

**Problem 1:** Write a SQL query to find the second highest salary from the `employees` table.
select e.name , e.salary
from employees e 
order by e.salary desc
limit 1 offset 1

**Problem 2:** Write a SQL query to find employees who were hired in the year 2024. 
select *
from employees e
where hire_date Between '2024-01-01'and '2024-12-31'

**Problem 3:** Write a SQL query to create a table called `orders` with columns: `order_id` (INT, PRIMARY KEY), `customer_name` (VARCHAR), `amount` (DECIMAL), `order_date` (DATE).
create table orders (
    order_id int primary key
    customer_name varchar
    amount decimal
    order_date date
)
### Part D — OOP Based Problem

Create a class `Animal` with a method `speak()`. Create two child classes `Dog` and `Cat` that inherit from `Animal` and override the `speak()` method. `Dog` should return "Woof!" and `Cat` should return "Meow!". Demonstrate polymorphism by calling `speak()` on both objects.
from abc import ABC,abstractmethod
class animal(ABC):
    @abstractmethod
    def speak(self):
        pass
    
class dog(animal):
    def speak(self):
        return "woof!"
class cat(animal):
    def speak(self):
        return "meow!"

cat1 = cat()
dog1 = dog()
print(cat1.speak())
print(dog1.speak())
### Part E — Django Based Problem

Set up a DRF `ModelViewSet` for a `Task` model with fields: `title`, `description`, `is_completed`, `created_at`. Register the viewset with a router and include the router URLs in `urls.py`. 

class task(models.modelviewset):
    
