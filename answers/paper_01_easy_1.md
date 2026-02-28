# 📝 Question Paper 01 — Easy 1

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is Python? Why is it popular for backend development? 

 python is a high level programing language , dynamically typed   most of the modern AI tech stack works well on python, huge support on libraries
2. What are the basic data types in Python? Name at least 5.
int,str,bool,float,list,tuple,set
3. What is the difference between a list and a tuple?
list is mutable , can store differnt datatypes , ordered. tuple is immutable ..we can modify tuple after creation
4. What is a dictionary in Python? Give a simple use case.
dictionary is a one of the datatype , which contains key , value pairs ...which denoted as a curly braces...the use case is if we building a small api based system the datas have been a json those json are stored as a dictionary
5. What is Django? Why do developers use it?
django is a full stack framework , which follow MVT architecture , have many inbuild features 
6. What does SQL stand for? What is it used for?
sql is a structured query language , it is a language used to speak with databases like mysql or postgres sql ...to get what we need from the dataset
7. What is a primary key in a database?
the primary key is a uniques key ...set when each row have been created mostly it was auto incremented ...it act like a connection bridge between tables
8. What is the difference between `GET` and `POST` HTTP methods? 
get and post are the common hhtp method ...get in simple term when a user want to read or fetch data get method have been called through a API , if we waant to write or add some datas we call the post method 
9. What is an API? Explain in simple terms.
api is a application programm inteface   whisch is used in most of the modern software development , api act like a bridge between the client the frontend and the server backend ...which uses rest archtecture have four methods get , post,put , patch
10. What is the difference between `==` and `is` in Python?

==  is used tom check wheather both datas are same 
is checks both are using the same reference or object

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What keyword is used to define a function in Python?
def
2. What built-in function returns the length of a list?
len()
3. What does `pip` stand for in Python?i just forgot it ...actualy it is a basic comman to install dependencies and libaries in python
4. What file extension do Python files use?
.py
5. In Django, what command creates a new project?
python admin startproject project_name
6. What SQL keyword is used to retrieve data from a table?
select
7. What does DRF stand for?
django REST framework
8. What symbol is used for single-line comments in Python?
  #
9. What method is used to add an element to the end of a list?
append()
10. In SQL, what keyword is used to filter rows?
group by

### Part B — Python Live Coding Problems

**Problem 1:** Write a Python function that takes a list of numbers and returns the sum of all even numbers.
```
Input:  [1, 2, 3, 4, 5, 6]
Output: 12

def sum(numbers):
    result=0
    for i in numbers:
        result += i
    return result

def sum(numbers):
    result = sum(numbers)
    return result
```

**Problem 2:** Write a Python program that prints numbers from 1 to 20. For multiples of 3, print "Fizz" instead of the number.
```
Output: 1, 2, Fizz, 4, 5, Fizz, 7, 8, Fizz, 10, 11, Fizz, 13, 14, Fizz, 16, 17, Fizz, 19, 20

def fizz(n):
    list=[]
    tables = 0
    for i in range(10):
        tables = tables + n
        list.append(tables)

    for i in range(1,21):
        if i in list:
            print("fizz")
        
        else :
            print(i) 
fizz(3)


def fizz_buzz():
    for i in range(1, 21):
        if i % 3 == 0:  # If the remainder is 0, it's a multiple of 3
            print("Fizz")
        else:
            print(i)

fizz_buzz()

```

**Problem 3:** Write a function that takes a string and returns it reversed.
```
Input:  "hello"
Output: "olleh"


def rev(word):
    rev = word[: : -1]
    return rev
```

### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name   | department | salary | hire_date  |
|--------|--------|------------|--------|------------|
| 1      | Ravi   | IT         | 45000  | 2023-01-15 |
| 2      | Priya  | HR         | 35000  | 2023-03-20 |
| 3      | Karan  | IT         | 55000  | 2024-06-10 |
| 4      | Anita  | Sales      | 28000  | 2022-11-05 |
| 5      | Suresh | HR         | 32000  | 2024-02-14 |

**Problem 1:** Write a SQL query to select all columns from the `employees` table.
                 
                select * 
                from employees e


**Problem 2:** Write a SQL query to find all employees whose `salary` is greater than 30000.
                select * 
                from employees e
                where salary > 30000

**Problem 3:** Write a SQL query to count the total number of rows in the `employees` table.
                select count(e.emp_id) as number_of_rows
                from employees e


### Part D — OOP Based Problem

Create a Python class called `Student` with the following:
- Attributes: `name`, `age`, `grade`
- A method `display_info()` that prints the student's details in a readable format
- Create 2 objects of this class and call the method


class student:
    def __init__(self,name,age,grade):
        self.name = name
        self.age = age 
        self.grade = grade
    def display_info(Self):
        return (f"student details \n student name : {Self.name} \n student age : {Self.age} \n student grade: {Self.grade}")

std1 = student("nanni",18,"A")
std2 = student ("mani",19,"C")
print(std1.display_info())
print(std2.display_info())


### Part E — Django Based Problem

Create a new Django project called `myshop`. Inside it, create an app called `products`. Define a model `Product` with fields: `name` (CharField), `price` (DecimalField), and `in_stock` (BooleanField). Register this model in the admin panel.

here i cant setup django ....so i start with model

in myshop/products/model.py
class product(models.model):
    name = models.charfiels(max_length = 30)
    price = models.Decimalfield()
    in_stock = models.BooleanField(default=False)