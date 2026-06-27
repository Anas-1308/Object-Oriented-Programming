Python Object-Oriented Programming (OOP) Essentials
A comprehensive reference guide covering core Object-Oriented Programming (OOP) concepts in Python, complete with clean code examples and implementations based on classroom interactive notebooks.

Table of Contents
Classes and Objects

Constructors (__init__)

Attributes and Methods

Static Methods

The 4 Pillars of OOP

Abstraction

Encapsulation (Public vs Private)

Inheritance

Polymorphism (Operator Overloading)

Utility Features (del keyword)

Classes and Objects
A Class is a blueprint or template for creating objects. An Object is an instance of a class that embodies the real-world entity.

Python
class Student:
    name = "Anas"

# Creating instances (objects)
s1 = Student()
print(s1.name)  # Output: Anas
Constructors (__init__)
Constructors are special methods used to initialize an object's state when it is created.

Default Constructor: A basic constructor that takes no arguments except self.

Parameterized Constructor: A constructor that accepts arguments to dynamically initialize instance variables.

Python
class Car:
    # Parameterized Constructor
    def __init__(self, clr, brand):
        self.clr = clr
        self.brand = brand
        print("Adding car to database...")

c1 = Car('blue', 'bmw')
Attributes and Methods
Class Attributes: Shared by all instances of the class (e.g., name = 'no name').

Instance (Object) Attributes: Unique to each individual object created from the class (defined via self).

Methods: Functions defined inside a class that operate on the object's data.

Python
class Student:
    name = 'no name'  # Class Attribute
    
    def __init__(self, name, year):
        self.name = name  # Instance Attribute
        self.year = year
        
    def welcome(self):
        print(f"Welcome {self.name}")
        
    def display_year(self):
        print(f"{self.name} is in {self.year} year")
Static Methods
Static methods perform an operation but don't need to access or modify the class or instance state. They do not accept the implicit self argument and are defined using the @staticmethod decorator.

Python
class StaticExample:
    @staticmethod
    def hello():
        print('hello')

StaticExample.hello()
The 4 Pillars of OOP
1. Abstraction
Hiding complex implementation details and exposing only the essential interface to the user.

Python
class Car:
    def __init__(self):
        self.acc = False
        self.brk = False
        
    def start(self):
        self.acc = False
        print("Car has started")  # User only sees the essential output
2. Encapsulation (Public vs Private)
Wrapping data and methods into a single unit and controlling accessibility.

Public Entities: Accessible anywhere inside or outside the class.

Private Entities: Declared using a double underscore prefix (__). They can only be accessed internally within the class structure.

Python
class Account:
    def __init__(self, accno, pswrd):
        self.accno = accno       # Public
        self.__pswrd = pswrd     # Private
        
    def login(self, trial):
        if trial == self.__pswrd:   # Internal access allowed
            print("Logged in")
3. Inheritance
The capability of a new class (derived/child) to inherit properties and behaviors from an existing class (base/parent).

Types Covered:
Single Inheritance: Child inherits directly from a single parent class.

Multi-level Inheritance: A class inherits from a child class, creating a chain of inheritance (Grandparent -> Parent -> Child).

super() Method: Used to access and invoke methods/constructors from the parent class.

Python
class Employee:
    def __init__(self, role, dept, sal):
        self.role = role
        self.dept = dept
        self.sal = sal

class Engineer(Employee):
    def __init__(self, name, age):
        self.name = name
        self.age = age
        # Call the parent constructor explicitly
        super().__init__("Engineer", "IT", "200000") 
4. Polymorphism (Operator Overloading)
Polymorphism allows different classes to be treated as if they were instances of the same class. A common application is Operator Overloading, where built-in operators (like + or -) are given custom behaviors by implementing special dunder methods like __add__ or __sub__.

Python
class Complex:
    def __init__(self, real, img):
        self.real = real
        self.img = img
        
    # Overloading the '+' operator
    def __add__(self, num2):
        return Complex(self.real + num2.real, self.img + num2.img)
Utility Features
The del Keyword
Used to explicitly destroy references to objects, variables, or elements, freeing up system memory. Trying to reference a deleted object will trigger an AttributeError or NameError.

Python
class Student:
    def __init__(self, name):
        self.name = name

s1 = Student("Anas")
del s1 
# print(s1.name) -> Raises Error because the instance no longer exists
