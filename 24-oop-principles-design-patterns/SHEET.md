# 🧩 Module 24: Object-Oriented Programming (OOP) & SOLID Design Patterns

Complete cheat-sheet for the 4 Pillar OOP principles, SOLID guidelines, and common software design patterns with code examples in C++, Java, and Python.

---

## 🏛️ 1. The 4 Pillars of OOP

1. **Encapsulation:** Bundling data (variables) and methods into a single unit (class) while restricting direct external access (`private`/`protected`).
2. **Abstraction:** Hiding complex background implementation details and showing only essential features to the user (Interface / Abstract class).
3. **Inheritance:** Enabling a child class to inherit fields and methods from a parent class (`extends` / `:`).
4. **Polymorphism:** Ability of a method to take many forms (Compile-time Method Overloading & Runtime Method Overriding).

---

## 📐 2. SOLID Design Principles

- **S - Single Responsibility Principle:** A class should have one, and only one, reason to change.
- **O - Open/Closed Principle:** Software entities should be open for extension, but closed for modification.
- **L - Liskov Substitution Principle:** Subtypes must be substitutable for their base types without altering program correctness.
- **I - Interface Segregation Principle:** Clients should not be forced to depend upon interfaces they do not use.
- **D - Dependency Inversion Principle:** High-level modules should not depend on low-level modules; both should depend on abstractions.

---

## 🛠️ 3. Essential Software Design Patterns

### A. Singleton Pattern (Creational)
Ensures a class has only one instance and provides a global point of access to it.

```python
class Singleton:
    _instance = None
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super(Singleton, cls).__new__(cls)
        return cls._instance
```

### B. Factory Pattern (Creational)
Creates objects without specifying the exact class of object that will be created.

### C. Strategy Pattern (Behavioral)
Defines a family of algorithms, encapsulates each one, and makes them interchangeable at runtime.
