## Inheritance in Python

### What is Inheritance?
Inheritance is a fundamental concept in Object-Oriented Programming (OOP) that allows a new class (called the child class) to inherit properties and behaviors (methods) from an existing class (called the parent class). This concept helps us to reuse code and extend the functionality of existing code without rewriting it.

### Why is Inheritance Useful?
Imagine you are building software for an e-commerce platform. You might have various types of users like customers, sellers, and admins. While all these users share some common properties (like a username or password), each user type also has specific features (like different access levels). Using inheritance, you can create a base class for general user properties, and extend it to handle specific cases for customers, sellers, and admins. This reduces redundancy and makes your code cleaner and easier to maintain.

### Key Benefits of Inheritance
Code Reusability: Write code once and reuse it across multiple classes.
Maintainability: Easier to maintain and update code when changes are needed.
Extensibility: Classes can be easily extended to add new functionality without modifying the existing code.
Modularity: Break your code into small, modular units that are easier to understand and maintain.
Basic Concepts of Inheritance in Python
Parent Class (Base Class): The class whose properties and methods are inherited.
Child Class (Derived Class): The class that inherits from the parent class.