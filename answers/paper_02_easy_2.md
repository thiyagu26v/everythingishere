# 📝 Question Paper 02 — Easy 2

---

## SECTION 1: VERBAL TECH ROUND (Face-to-Face)

> 10 technical questions — answer verbally

1. What is the difference between a mutable and immutable object in Python? Give examples.
mutable we can modify the data after creation , example list of numbers .....immutable we cant modify eg tuple datatype
2. What is a virtual environment in Python? Why do we use it?
virtual environment is a isolated folder where it did not connect directly in our project folder , which stores the project required dependecies , secured passwords or databse details ...to avoid collions with other users and it helps to handle the version what others use
3. Explain what `urls.py` does in a Django project.

urls.py is the which contains our projects url configuration which maps with the views or apiviews in the main files , in real projects which is act like a api endpoints
4. What is a foreign key in a database?
koreign keys are unique keys which used to make connection between two different tables and it actualy act lkike a brige between two tables
5. What are Python decorators? Give a basic idea.
decorators is a mostuseful concept in python where we can add extra functionalites to the existing function without diresctly touching it ...there are some inbuilt decorators in python @property  @action
6. What is the difference between `NULL` and `NOT NULL` in SQL?
null checks if the field is empty , not null used when we want the field is not be empty
7. What is the purpose of `settings.py` in Django?
8. What is a REST API?
first api is a application programm interface which act like a brige between the client frontend and the server backend , we actualy write apis in our backend file which works when the frontend triggers  the api enpoint 
here the api follow a architechture called REST which have four major works read get , write post , update put patch , deleted delete
9. What is the difference between `append()` and `extend()` in Python lists?
both are a inbuilt functions in python used to modify sequence datatypes ...for example in a list we use append to add a data at the end of the list ,,,and extend we use to add or combine the left list and the right list
10. What are HTTP status codes? Name a few common ones. 
status code mostly used to tell the client side what actually happening through http methods ...for example 404 not found , 202 400 ....

---

## SECTION 2: TASK ROUND (Live Technical)

### Part A — One-Word / Short Answers (10 Questions)

1. What keyword is used to create a class in Python?
class
2. What Django command runs the development server?
python manage.py runserver
3. In SQL, what keyword is used to sort results?
select
4. What is the default port number for Django's development server?8000
5. What Python keyword is used to handle exceptions? except
6. What SQL keyword removes duplicate rows from results? distinct
7. What does `ORM` stand for? object relational mapping
8. What method converts a string to lowercase in Python? .lower()
9. What Django command applies database migrations? python manage.py make migration
python manage.py migrate
10. What data structure uses key-value pairs in Python? dict  - dictionary

### Part B — Python Live Coding Problems

**Problem 1:** Write a function that takes a list of numbers and returns the largest number without using the `max()` function.
```
Input:  [3, 7, 2, 9, 5]
Output: 9
```
def max(numbers):
    result= 0
    for i in numbers:
        if i > result:
            result = i
    return result

**Problem 2:** Write a program that checks whether a given string is a palindrome or not.
```
Input:  "madam"
Output: True

Input:  "hello"
Output: False

def palidrome(word):
    rev = word[::-1]
    if  rev.lower() == word.lower():
        return True
    else:
        return False


```

**Problem 3:** Write a function that takes two lists and returns a new list containing only the common elements.
```
Input:  [1, 2, 3, 4], [3, 4, 5, 6]
Output: [3, 4]
```
def common(arr1,arr2):
    result = []
    for i in arr1:
        if i in arr2:
            result.appent(i)
    return result

def common(arr1,arr2):
    result = arr1.intersection(arr2)
    return result



### Part C — SQL Live Problems

**Use this table for all problems:**

**Table: employees**
| emp_id | name    | department | salary | hire_date  |
|--------|---------|------------|--------|------------|
| 1      | Ravi    | IT         | 50000  | 2023-01-15 |
| 2      | Priya   | HR         | 38000  | 2023-05-10 |
| 3      | Karan   | IT         | 62000  | 2022-08-20 |
| 4      | Meena   | Finance    | 45000  | 2024-01-12 |
| 5      | Arjun   | IT         | 55000  | 2023-11-30 |
| 6      | Divya   | HR         | 40000  | 2024-03-18 |

**Problem 1:** Write a SQL query to select the `name` and `salary` of employees from the `employees` table, ordered by salary in descending order.

                select e.name , e.salary
                from employees e
                order by e.salary DESC
**Problem 2:** Write a SQL query to find employees who work in the `'IT'` department.
            select *
            from employees e
            where e.department = "IT"
             
**Problem 3:** Write a SQL query to get the average salary of all employees.
                select avg(salary) as avaerage salary
                from employees e


### Part D — OOP Based Problem

Create a class `BankAccount` with:
- Attributes: `account_holder`, `balance`
- Methods: `deposit(amount)`, `withdraw(amount)`, `check_balance()`
- The withdraw method should not allow withdrawal if the amount exceeds the balance
- Create an object, deposit 5000, withdraw 2000, and check the balance
class Bankaccount:
    def __init__(self,account_holder,balance):
        self.account_holder= account_holder
        self.balance = balance
        
    def deposit(self,amount):
        self.balance = self.balance + amount
        return f"amount : {amount} sucessfully depostited"
    def withdrawal(self,amount):
        self.balance = self.balance - amount
        return f"amount : {amount} withdrawed succesfully"
    def check_balance(self):
        return (f"hi {self.account_holder}\n your current balance :{self.balance}")
    
user1 = Bankaccount("nanni", 7000)

print(user1.withdrawal(3000))
print(user1.check_balance())
print(user1.deposit(1000))
print(user1.check_balance())
### Part E — Django Based Problem

In an existing Django project, create an app called `blog`. Define a model `Post` with fields: `title` (CharField), `content` (TextField), `created_at` (DateTimeField with auto_now_add). Create and apply the migration for this model.



class post(models.model):
    title = models.charfiels(max_length=100)
    content= models.textfield()
    created_at = models.DateTimeField(auto_now_add = True)


on terminal
python manage.py make migration
python manage.py migrate