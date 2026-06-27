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
