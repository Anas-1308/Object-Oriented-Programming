# PYTHON OBJECT-ORIENTED PROGRAMMING (OOP) ESSENTIALS

A comprehensive reference guide covering core Object-Oriented Programming (OOP) concepts in Python, complete with clean code examples and implementations based on classroom interactive notebooks.

## TABLE OF CONTENTS
* [Classes and Objects](#classes-and-objects)
* [Constructors (`__init__`)](#constructors-__init__)
* [Attributes and Methods](#attributes-and-methods)
* [Static Methods](#static-methods)
* [The 4 Pillars of OOP](#the-4-pillars-of-oop)
  * [Abstraction](#1-abstraction)
  * [Encapsulation (Public vs Private)](#2-encapsulation-public-vs-private)
  * [Inheritance](#3-inheritance)
  * [Polymorphism (Operator Overloading)](#4-polymorphism-operator-overloading)
* [Utility Features (`del` keyword)](#utility-features)

---

## CLASSES AND OBJECTS

A **Class** is a blueprint or template for creating objects. An **Object** is an instance of a class that embodies the real-world entity.

```python
class Student:
    name = "Anas"

# Creating instances (objects)
s1 = Student()
print(s1.name)  # Output: Anas
```
## CONSTRUCTORS (__init__)
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
Note: Python does not support multiple constructor definitions in the same class like some other languages. If multiple __init__ methods are defined, the last one will overwrite the previous ones.

ATTRIBUTES AND METHODS
Class Attributes: Shared by all instances of the class (e.g., name = 'no name').

Instance (Object) Attributes: Unique to each individual object created from the class, defined via self.

Methods: Functions defined inside a class that operate on the object's data.

Python
class Student:
    name = 'no name'  # Class Attribute
    
    def __init__(self, name, year):
        self.name = name  # Instance Attribute
        self.year = year
        
    def Welcome(self):
        print(f"Welcome {self.name}")
        
    def DisplayYear(self):
        print(f"{self.name} is in {self.year} year")
STATIC METHODS
Static methods perform an operation but do not require access to instance or class data (they don't use self). They are declared using the @staticmethod decorator.

Python
class StaticExample:
    @staticmethod
    def hello():
        print('hello')

s = StaticExample()
s.hello()
THE 4 PILLARS OF OOP
1. ABSTRACTION
Hiding internal implementation details of a class and showing only essential features to the user.

Python
class Car:
    def __init__(self):
        self.acc = False
        self.brk = False
        self.clutch = False
        
    def Start(self):
        self.acc = False
        self.clutch = False
        print("Car has started")  # User only sees this essential message
2. ENCAPSULATION (PUBLIC VS PRIVATE)
Wrapping data and methods into a single unit and controlling accessibility.

Public Entities: Accessible anywhere inside or outside the class by default.

Private Entities: Declared using a double underscore prefix (__) to prevent access from outside the class.

Python
class Account:
    def __init__(self, accno, pswrd):
        self.accno = accno       # Public entity
        self.__pswrd = pswrd     # Private entity
        
    def LoginMethod(self, trial):
        if trial == self.__pswrd:   # Internal access within class is allowed
            print("Logged in")
3. INHERITANCE
The capability of a new class (child) to inherit properties and behaviors from an existing class (parent).

Types Covered:
Single Inheritance: A child class inherits properties directly from a single parent class.

Multi-level Inheritance: A chain of inheritance where a class inherits from a derived child class.

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
        # Access parent constructor using super()
        super().__init__("Engineer", "IT", "200000") 
4. POLYMORPHISM (OPERATOR OVERLOADING)
Allowing distinct types of objects to respond to the same interface or operation. Custom behavior for built-in operators is achieved using special dunder methods like __add__ or __sub__.

Python
class Complex:
    def __init__(self, real, img):
        self.real = real
        self.img = img
        
    # Overloading the '+' operator
    def __add__(self, num2):
        newReal = self.real + num2.real
        newimg = self.img + num2.img 
        return Complex(newReal, newimg)
UTILITY FEATURES
THE del KEYWORD
Used to explicitly delete references to objects. Attempting to reference a deleted object will trigger an error since the instance no longer exists.

Python
class Student:
    def __init__(self, name):
        self.name = name

s1 = Student("Anas")
del s1 
# print(s1.name) -> Raises Error because s1 has been deleted
