# Java OOP Concepts - Easy Guide

This guide covers key Object-Oriented Programming (OOP) concepts in Java, with clear definitions and practical examples.

---

## 1. Object & Class in Java

### Class

A class is like a blueprint or template. It defines what properties (variables) and behaviors (methods) an object can have.

### Object

An object is a real-world entity created from a class. It has a state (variables) and behavior (methods).

#### Example:

```java
class Car {
    String color = "Red"; // property

    void drive() {        // behavior
        System.out.println("Car is driving");
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car(); // creating an object of Car
        myCar.drive();         // calling method
        System.out.println(myCar.color); // accessing property
    }
}
```

---

## 2. Constructor Overloading

A **constructor** is a special method used to initialize objects. Constructor **overloading** means creating multiple constructors with different parameters.

#### Example:

```java
class Student {
    String name;
    int age;

    // Constructor with one parameter
    Student(String name) {
        this.name = name;
    }

    // Constructor with two parameters
    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

---

## 3. Inheritance & Aggregation

### Inheritance (IS-A relationship)

One class (child/subclass) inherits properties and methods from another class (parent/superclass). Promotes code reusability.

#### Example:

```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}
```

### Aggregation (HAS-A relationship)

A class contains an object of another class. It is a weaker relationship than inheritance.

#### Example:

```java
class Engine {
    void start() {
        System.out.println("Engine started");
    }
}

class Car {
    Engine engine = new Engine(); // Aggregation

    void startCar() {
        engine.start();
        System.out.println("Car started");
    }
}
```

### Comparison Table:

| Feature      | Inheritance (IS-A) | Aggregation (HAS-A) |
| ------------ | ------------------ | ------------------- |
| Relationship | Parent-Child       | Containment         |
| Reusability  | High               | Medium              |
| Coupling     | Tight              | Loose               |
| Flexibility  | Less               | More                |

---

## 4. Access Modifiers

Access modifiers define the scope (visibility) of variables and methods.

| Modifier    | Within Class | Same Package | Subclass | Outside Package   |
| ----------- | ------------ | ------------ | -------- | ----------------- |
| `private`   | Yes          | No           | No       | No                |
| (default)   | Yes          | Yes          | Yes      | No                |
| `protected` | Yes          | Yes          | Yes      | Yes (if subclass) |
| `public`    | Yes          | Yes          | Yes      | Yes               |

#### Example:

```java
public class Person {
    private String name;       // Only within class
    protected int age;         // Within class, package, subclass
    public String gender;      // Everywhere

    public void setName(String name) {
        this.name = name; // Encapsulated via setter
    }
}
```

---

## 5. Polymorphism

Polymorphism means "many forms". A single function behaves differently in different situations.

### Compile-Time Polymorphism (Method Overloading)

Same method name with different parameters.

```java
class MathUtil {
    int add(int a, int b) {
        return a + b;
    }
    int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

### Run-Time Polymorphism (Method Overriding)

Subclass changes the implementation of a method in its superclass.

```java
class Animal {
    void makeSound() {
        System.out.println("Animal sound");
    }
}

class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Meow");
    }
}
```

---

## 6. Referencing Subclass Objects

```java
Dog d = new Dog();        // Subclass reference to subclass object
Animal a = new Dog();     // Superclass reference to subclass object
```

* You can call overridden methods with superclass reference.
* You cannot access methods unique to subclass if reference is of superclass.

---

## 7. Abstraction & Encapsulation

### Abstraction

Hiding complex implementation and showing only essential details.

#### Example:

```java
abstract class Vehicle {
    abstract void run();
}

class Bike extends Vehicle {
    void run() {
        System.out.println("Bike is running");
    }
}
```

### Encapsulation

Binding data (variables) and code (methods) together and restricting direct access.

#### Example:

```java
class Employee {
    private String name;

    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
}
```

### Importance

* Ensures data security
* Easy to change and maintain code
* Improves reusability and flexibility

---

## 8. Static Classes, Methods, Inner & Outer Classes

### Static Method

Belongs to the class, not to objects.

### Inner Classes

Classes inside another class.

#### Example:

```java
class Outer {
    static class StaticInner {
        void display() {
            System.out.println("Static Inner Class");
        }
    }

    class NonStaticInner {
        void show() {
            System.out.println("Non-Static Inner Class");
        }
    }

    static void staticMethod() {
        System.out.println("Static Method of Outer class");
    }
}
```

---

## 9. Interfaces & Enums

### Interface

An interface contains only abstract methods (before Java 8). It is implemented by classes.

#### Example:

```java
interface Animal {
    void eat();
}

class Cow implements Animal {
    public void eat() {
        System.out.println("Cow eats grass");
    }
}
```

### Enum

A special class to define constants.

#### Example:

```java
enum Day {
    MONDAY, TUESDAY, WEDNESDAY;
}

public class TestEnum {
    public static void main(String[] args) {
        Day today = Day.MONDAY;
        System.out.println("Today is " + today);
    }
}
```

---


