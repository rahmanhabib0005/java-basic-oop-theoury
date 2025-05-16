# Java OOP Concepts - Easy Guide

## 1. Object & Class in Java

* **Class**: A blueprint for objects. It defines properties (fields) and behaviors (methods).
* **Object**: An instance of a class.

```java
class Car {
    String color = "Red";
    void drive() {
        System.out.println("Car is driving");
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car(); // object
        myCar.drive();
        System.out.println(myCar.color);
    }
}
```

---

## 2. Constructor Overloading

Same class having multiple constructors with different parameters.

```java
class Student {
    String name;
    int age;

    Student(String name) {
        this.name = name;
    }

    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

---

## 3. Inheritance & Aggregation

### Inheritance

* One class inherits another class.

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

### Aggregation

* Has-A relationship (use of object inside another class).

```java
class Engine {
    void start() {
        System.out.println("Engine started");
    }
}

class Car {
    Engine engine = new Engine();
    void startCar() {
        engine.start();
        System.out.println("Car started");
    }
}
```

### Comparison

| Feature      | Inheritance | Aggregation |
| ------------ | ----------- | ----------- |
| Relationship | IS-A        | HAS-A       |
| Reusability  | High        | Medium      |
| Coupling     | Tight       | Loose       |

---

## 4. Access Modifiers

| Modifier  | Same Class | Same Package | Subclass | Other Package     |
| --------- | ---------- | ------------ | -------- | ----------------- |
| private   | Yes        | No           | No       | No                |
| default   | Yes        | Yes          | Yes      | No                |
| protected | Yes        | Yes          | Yes      | Yes (if subclass) |
| public    | Yes        | Yes          | Yes      | Yes               |

```java
public class Person {
    private String name;
    protected int age;
    public String gender;

    public void setName(String name) {
        this.name = name;
    }
}
```

---

## 5. Polymorphism

### Overloading (Compile Time)

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

### Overriding (Run Time)

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
Dog d = new Dog();         // Subclass reference to subclass object
Animal a = new Dog();      // Superclass reference to subclass object
```

* With superclass reference, you can only access methods available in the superclass unless overridden.

---

## 7. Abstraction & Encapsulation

### Abstraction

* Hiding internal details and showing only essential info.

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

* Binding data and methods in a single unit and restricting direct access.

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

### Importance in OOP

* Improves modularity, reusability, and maintainability
* Reduces complexity by hiding details

---

## 8. Static Classes, Methods, Inner & Outer Classes

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
        System.out.println("Static Method");
    }
}
```

---

## 9. Interfaces & Enums

### Interface

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

```java
enum Day {
    MONDAY, TUESDAY, WEDNESDAY;
}

public class TestEnum {
    public static void main(String[] args) {
        Day d = Day.MONDAY;
        System.out.println(d);
    }
}
```

---

Feel free to use this file as a basic reference for understanding OOP concepts in Java.
