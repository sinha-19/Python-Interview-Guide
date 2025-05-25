# 4. Object-Oriented Programming in Python

---

## What is OOP?

- **Object-Oriented Programming (OOP):** Programming paradigm based on objects (data + behavior).
- Python supports OOP: classes, inheritance, encapsulation, polymorphism.

---

## Classes and Objects

```python
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        print(f"{self.name} says Woof!")

my_dog = Dog("Fido")
my_dog.bark()  # Output: Fido says Woof!
```

- `__init__` is the constructor.
- `self` refers to the current instance.

---

## Instance & Class Variables

```python
class Cat:
    species = "Felis catus"  # Class variable (shared)
    def __init__(self, name):
        self.name = name      # Instance variable (unique)

c1 = Cat("Tom")
c2 = Cat("Jerry")
```

---

## Inheritance

```python
class Animal:
    def speak(self):
        print("Some sound")

class Dog(Animal):
    def speak(self):
        print("Woof!")
```

---

## Method Overriding

- Child class can override parent methods.
- Use `super()` to call parent methods.

```python
class Parent:
    def show(self):
        print("Parent")

class Child(Parent):
    def show(self):
        super().show()
        print("Child")
```

---

## Encapsulation

- Private attributes: prefix with `_` or `__` (name mangling for `__`).
- Python does not enforce true privacy; naming is by convention.

```python
class Example:
    def __init__(self):
        self._protected = 1
        self.__private = 2
```

---

## Polymorphism

- Same interface, different implementations.

```python
class Bird:
    def speak(self):
        print("Tweet")

class Duck:
    def speak(self):
        print("Quack")

for animal in [Bird(), Duck()]:
    animal.speak()
```

---

## Special Methods (Magic/Dunder Methods)

- Customize behavior for built-in functions.

| Method        | Purpose                         |
|---------------|--------------------------------|
| `__str__`     | String representation          |
| `__repr__`    | Official string representation |
| `__len__`     | Length (`len(obj)`)            |
| `__eq__`      | Equality (`==`)                |
| `__lt__`      | Less than (`<`)                |

---

## Common Pitfalls

- Forgetting `self` as the first method parameter.
- Accidentally overwriting class variables with instance variables.
- Misusing private/protected naming conventions.

---

## Interview Tips

- Be able to design and implement a simple class hierarchy.
- Understand the difference between class and instance variables.
- Know the basics of inheritance and method overriding.

---

## Possible Follow-Up Questions

- How do you implement multiple inheritance in Python?
- What is the difference between `__str__` and `__repr__`?
- How can you make an attribute "private" in Python?
- What is the MRO (method resolution order)?
