# Module 2: Intermediate Programming Concepts

## Lesson 2: Object-Oriented Programming (OOP) in Python

### Topics
1. Classes and Objects
2. Inheritance
3. Encapsulation
4. Polymorphism

---

### 1. Classes and Objects

Here’s the updated explanation with Flutter included in the list of OOP languages and an example tailored for someone in the finance sector:

---

### Object-Oriented Programming (OOP)

#### Overview
Object-Oriented Programming (OOP) is a programming paradigm based on the concept of "objects." Objects can contain data, in the form of fields (often known as properties or attributes), and code, in the form of procedures (often known as methods).

- **Class**: A blueprint for creating objects (a particular data structure).
  - Think of a class as a template or a blueprint. For example, consider a class called `Car`. The `Car` class would define what properties a car has (like `color`, `brand`, `model`, etc.) and what actions a car can perform (like `drive`, `stop`, `honk`, etc.).
  
- **Object**: An instance of a class.
  - When you create a specific car (like your red Toyota Corolla), you are creating an object based on the `Car` class. This specific car object would have its own unique values for the properties defined by the `Car` class (e.g., `color` might be `red`, `brand` might be `Toyota`, and `model` might be `Corolla`).

### Example 1 in Python

**Defining a Class**
```python
class Car:
    def __init__(self, brand, model, color):
        self.brand = brand
        self.model = model
        self.color = color

    def drive(self):
        return f"The {self.color} {self.brand} {self.model} is driving."

    def stop(self):
        return f"The {self.color} {self.brand} {self.model} has stopped."

# Creating an Object
my_car = Car("Toyota", "Corolla", "red")

# Using the Object
print(my_car.drive())  # Output: The red Toyota Corolla is driving.
print(my_car.stop())   # Output: The red Toyota Corolla has stopped.
```
### Example 3 Creating a Class
```python
class Dog:
    # Class attribute
    species = "Canis familiaris"
    
    # Initializer / Instance attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    # Instance method
    def description(self):
        return f"{self.name} is {self.age} years old."
    
    # Another instance method
    def speak(self, sound):
        return f"{self.name} says {sound}."
```

#### Creating an Object
```python
# Creating instances of the Dog class
dog1 = Dog("Buddy", 3)
dog2 = Dog("Milo", 5)

# Accessing attributes and methods
print(dog1.description())  # Output: Buddy is 3 years old.
print(dog2.speak("Woof Woof"))  # Output: Milo says Woof Woof.
```

---

In this example, `Car` is a class with an initializer method (`__init__`) that sets the properties of the car (`brand`, `model`, `color`). It also has methods (`drive` and `stop`) that define actions the car can perform. `my_car` is an object (instance) of the `Car` class with specific values for its properties.

### Importance of OOP

1. **Modularity**: OOP allows you to break down a complex problem into smaller, more manageable pieces (objects). Each piece can be developed, tested, and debugged independently.

2. **Reusability**: Once a class is written, it can be reused across different programs. You can create multiple objects from a single class, each with different values for its properties.

3. **Scalability**: OOP makes it easier to scale your application. You can create new classes and objects that build on existing ones, adding new functionality as needed.

4. **Maintainability**: OOP code is easier to maintain because it’s organized into objects that represent real-world entities. Changes to one part of the program are less likely to affect other parts, making your codebase more robust and easier to manage.

5. **Encapsulation**: Encapsulation is the bundling of data and methods that operate on the data into a single unit or class. It restricts direct access to some of the object's components, which is a means of preventing accidental interference and misuse of the methods and data.

6. **Inheritance**: Inheritance is a mechanism for creating a new class that is a modified version of an existing class. It promotes code reuse and can lead to a natural hierarchy of classes.

7. **Polymorphism**: Polymorphism allows you to use a unified interface to interact with objects of different classes. This means that objects of different types can be accessed through the same interface, simplifying code and reducing complexity.

#### Languages that Implement OOP

Many programming languages support OOP principles. Some of the most popular OOP languages include:

- **Python**: Known for its simplicity and readability, Python is widely used for web development, data science, automation, and more.
- **Java**: A versatile and widely-used language, particularly in large enterprise environments, web development, and Android app development.
- **C++**: An extension of the C programming language, C++ is used in game development, real-time systems, and performance-critical applications.
- **C#**: Developed by Microsoft, C# is used for a wide range of applications, including web, mobile, and desktop applications, particularly within the .NET framework.
- **Ruby**: Known for its simplicity and productivity, Ruby is often used in web development, especially with the Ruby on Rails framework.
- **JavaScript**: Primarily used for web development, JavaScript can also be used in server-side development with environments like Node.js.
- **PHP**: Widely used for server-side web development, PHP supports object-oriented programming features.
- **Dart/Flutter**: Dart is the language used with the Flutter framework for building cross-platform mobile, web, and desktop applications. It supports OOP principles extensively.

---

### Example 2

Let's consider a simple example of how OOP can be used in a finance-related application. Suppose we are building a system to manage different types of bank accounts.

**Defining a Class in Python**
```python
class BankAccount:
    def __init__(self, account_number, account_holder, balance=0.0):
        self.account_number = account_number
        self.account_holder = account_holder
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        return f"Deposited {amount}. New balance is {self.balance}"

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
            return f"Withdrew {amount}. New balance is {self.balance}"
        else:
            return "Insufficient funds"

# Creating an Object
account = BankAccount("123456", "John Doe", 1000.0)

# Using the Object
print(account.deposit(500))   # Output: Deposited 500. New balance is 1500.0
print(account.withdraw(200))  # Output: Withdrew 200. New balance is 1300.0
print(account.withdraw(2000)) # Output: Insufficient funds
```

In this example, `BankAccount` is a class that represents a bank account with properties like `account_number`, `account_holder`, and `balance`. It has methods to `deposit` and `withdraw` money. An object of the class is created with specific values, and the methods are called to perform operations on the account.

This approach can be extended to manage different types of accounts (e.g., savings, checking) by creating subclasses that inherit from `BankAccount` and add specific features or constraints.

---

### 2. Inheritance

#### Overview
Inheritance allows a class to inherit attributes and methods from another class.

#### Creating a Parent Class
```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        raise NotImplementedError("Subclasses must implement this method")
```

#### Creating a Child Class
```python
class Cat(Animal):
    def speak(self):
        return f"{self.name} says Meow"

class Dog(Animal):
    def speak(self):
        return f"{self.name} says Woof"
```

#### Using Inheritance
```python
cat = Cat("Whiskers")
dog = Dog("Buddy")

print(cat.speak())  # Output: Whiskers says Meow
print(dog.speak())  # Output: Buddy says Woof
```

Here are two additional examples to illustrate inheritance: one using cars and the other using people.

### Example 1: Using Cars

#### Creating a Parent Class
```python
class Vehicle:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year

    def start_engine(self):
        return "The engine is starting..."

    def stop_engine(self):
        return "The engine is stopping..."
```

#### Creating Child Classes
```python
class Car(Vehicle):
    def start_engine(self):
        return f"The {self.year} {self.make} {self.model}'s engine is starting with a roar!"

class ElectricCar(Vehicle):
    def start_engine(self):
        return f"The {self.year} {self.make} {self.model}'s electric engine is starting silently."

class Motorcycle(Vehicle):
    def start_engine(self):
        return f"The {self.year} {self.make} {self.model}'s engine is starting with a vroom!"
```

#### Using Inheritance
```python
car = Car("Toyota", "Axio", 2016)
electric_car = ElectricCar("Fortuner", "Hybrid", 2016)
motorcycle = Motorcycle("Tiger", "Motorcycle", 2010)

print(car.start_engine())        # Output: The 2016 Toyota Axio's engine is starting with a roar!
print(electric_car.start_engine()) # Output: The 2016 Fortuner Hybrid engine is starting silently.
print(motorcycle.start_engine())   # Output: The 2010 Tiger MotorCycle engine is starting with a vroom!
```

### Example 2: 

#### Creating a Parent Class
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):
        return f"Hello, my name is {self.name} and I am {self.age} years old."
```

#### Creating Child Classes
```python
class Student(Person):
    def __init__(self, name, age, school):
        super().__init__(name, age)
        self.school = school

    def introduce(self):
        return f"Hello, my name is {self.name}, I am {self.age} years old, and I study at {self.school}."

class Teacher(Person):
    def __init__(self, name, age, subject):
        super().__init__(name, age)
        self.subject = subject

    def introduce(self):
        return f"Hello, my name is {self.name}, I am {self.age} years old, and I teach {self.subject}."
```

#### Using Inheritance
```python
student = Student("Alice", 20, "Modcom Institute")
teacher = Teacher("Kamau", 45, "Programming")

print(student.introduce())  # Output: Hello, my name is Alice, I am 20 years old, and I study at XYZ University.
print(teacher.introduce())  # Output: Hello, my name is Mr. Smith, I am 45 years old, and I teach Mathematics.
```

---

### 3. Encapsulation

#### Overview
Encapsulation is the concept of wrapping data (variables) and methods (functions) that work on the data into a single unit or class. It restricts direct access to some of the object's components, which is a means of preventing accidental interference and misuse of the methods and data.

#### Example with Private Variables
```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.__year = year  # Private attribute
    
    def get_year(self):
        return self.__year
    
    def set_year(self, year):
        if year > 1885:  # The first car was made in 1886
            self.__year = year
        else:
            print("Invalid year")
```

#### Using Encapsulation
```python
car = Car("Toyota", "Corolla", 2015)
print(car.get_year())  # Output: 2015

car.set_year(2020)
print(car.get_year())  # Output: 2020

car.set_year(1800)  # Output: Invalid year
```

---

### 4. Polymorphism

#### Overview
Polymorphism allows for using a unified interface to interact with different types of objects.

#### Example with Methods
```python
class Bird:
    def __init__(self, name):
        self.name = name
    
    def fly(self):
        return f"{self.name} can fly"

class Penguin(Bird):
    def fly(self):
        return f"{self.name} can't fly but can swim"
```

#### Using Polymorphism
```python
bird = Bird("Sparrow")
penguin = Penguin("Pingu")

animals = [bird, penguin]

for animal in animals:
    print(animal.fly())

# Output:
# Sparrow can fly
# Pingu can't fly but can swim
```

#### Example with Functions
```python
def animal_speak(animal):
    print(animal.speak())

class Dog:
    def speak(self):
        return "Woof"

class Cat:
    def speak(self):
        return "Meow"

dog = Dog()
cat = Cat()

animal_speak(dog)  # Output: Woof
animal_speak(cat)  # Output: Meow
```

---

### Conclusion
Object-Oriented Programming (OOP) is a powerful paradigm in Python that helps in organizing code in a way that is both reusable and maintainable. By understanding classes, inheritance, encapsulation, and polymorphism, you can design more robust and flexible software.

---



