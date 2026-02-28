# 📝 Question Paper 03 — Easy 3

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between a function and a method in Python?
methods are also a funtion written inside any class and every method takes self as a argument function are written independently without inside a class they only take arugumensts
2. What is `manage.py` in Django?
its a command line utility command which is used to run our code ..for example we use python manage .py runserver to run server and python manage.py migrate for migrate database models ..its the mail file contains our mair details odf the projecvt to run it
3. What are the different types of SQL joins? Explain briefly.
join or inner join ..which is used to join two tables union datas
left join which is gives all rows and coloums from the left tabele and matching from the right table 
right join ..actuall like same as left join but it give all datas from right table 
4. What is list comprehension in Python? Give a simple example verbally.
list comprehension is a simple way to create a list or work with list datatypes   for example k = i for i in list[1]
5. What is the purpose of `models.py` in Django?
models,py the one of the main file in django apps which have the configurations of our data base table ..each class inside a model.py file denotes a table and each attribute defines the coloum name
6. What is the difference between `CHAR` and `VARCHAR` in SQL?
char used only for alphabatics varchar is for integer and char or any thing in the keyboard
7. What is `__init__` method in Python? Why is it used?
__init__ is a very useful method its mostly used in oops concepts actually it works as a constructor for the class if we declared a variable as self.variable name ...it auto assing values to all method inside the class in self ....and it automatically called when the object of the class creator 
8. What is serialization in the context of DRF?
serialiization is a important topic in drf ...because it is used to validate the datas from the post api calls ,,,and which used to convert python objects to a json format and sent it on a get api call 
9. What is the difference between `while` loop and `for` loop?
both are used for loops but the major difference is the for loop runs until it hits the last range on while it runs until it fullfill the condition
10. What is CRUD? What does each letter stand for?
crud operations mostly we used crud with the api calls and with the models ...which is actualy used for create ,read,update, and delete


---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What Python keyword is used to import a module? from ...imoprt..

2. What SQL clause limits the number of rows returned?
limit
3. What Django file defines database models?
models.py
4. What built-in function converts a string to an integer in Python?
int()
5. What HTTP method is typically used to delete a resource? def delete
6. What Python method removes an item from a list by value? remove()
7. What does `CSRF` stand for? cross site request forgery
8. What SQL keyword is used to update existing records? update
9. What is the file name for Django URL configuration? urls.py
10. What Python keyword creates a generator? yield

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a number and returns `True` if it's a prime number, `False` otherwise.
```
Input:  7
Output: True

Input:  10
Output: False

def num(n):
    if n % 2 = 0:
        return True
    else :
        return False
```

**Problem 2:** Write a program that counts the frequency of each character in a given string and returns it as a dictionary.
```
Input:  "banana"
Output: {"b": 1, "a": 3, "n": 2}

def count_char(word):
    result={}
    for i in word:
        result[i]=result.get(i,o)+1
    else :
        result [i] = 1

```

**Problem 3:** Write a function that takes a list of integers and returns a new list with duplicates removed (without using `set()`).
```
Input:  [1, 2, 2, 3, 4, 4, 5]
Output: [1, 2, 3, 4, 5] 

def rem_Dup(arr):
    result = []
    for i in arr:
        if i not in result:
            result.appen(i)
        
    return result
```

### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name   | department | salary |
|--------|--------|------------|--------|
| 1      | Ravi   | IT         | 40000  |
| 2      | Priya  | HR         | 35000  |
| 3      | Karan  | Sales      | 42000  |
| 4      | Anita  | HR         | 38000  |
| 5      | Suresh | IT         | 50000  |

**Problem 1:** Write a SQL query to insert a new row into the `employees` table with values for `name`, `department`, and `salary`.
insert into employees e (e.name,e.department,e.salary)
values("nanni,"CEO",100000)
**Problem 2:** Write a SQL query to update the salary of an employee named 'Ravi' to 45000.
update employees e
set e.salary = 45000
where e.name = "Ravi 
"

**Problem 3:** Write a SQL query to delete all employees from the `employees` table who belong to the `'HR'` department.

delete from employees e 
where e.department = "HR"

### Part D — OOP Based Problem

Create a class `Rectangle` with:
- Attributes: `length`, `width`
- Methods: `area()` and `perimeter()`
- Add a `__str__` method that returns a readable description of the rectangle
- Create 2 rectangle objects and print their area and perimeter


class Rectangle():
    def __init__(self,length,width):
        self.length = length
        self.width = width
        
    def __str__(self):
        return f"width :{self.width}\n length : {self.length} \n area :{self.area()} width : {self.perimeter()}"
        
    def area(self):
        area = self.length * self .width
        return area
        
    def perimeter(self):
        perimeter = 2* (self.length + self.width)
        return perimeter

rect1 = Rectangle(9,2)
rect2 = Rectangle(7,5)

print(rect1.area())

print(rect1.perimeter())

print(rect2.area())

print(rect2.perimeter())


print(rect1)
 

 

### Part E — Django Based Problem

Create a Django view (function-based) that returns a JSON response containing a list of 3 sample book titles. Map this view to the URL `/api/books/`.


