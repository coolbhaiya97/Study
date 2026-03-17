# 07 – Object-Oriented Programming (OOP)

## The Four Pillars of OOP
1. **Encapsulation** – hiding internal data
2. **Inheritance** – reusing code from a parent class
3. **Polymorphism** – one interface, multiple behaviours
4. **Abstraction** – showing only essential details

---

## Classes and Objects

```java
// Class definition
class Car {
    // Fields (attributes)
    String brand;
    int speed;

    // Constructor
    Car(String brand, int speed) {
        this.brand = brand;
        this.speed = speed;
    }

    // Method (behaviour)
    void displayInfo() {
        System.out.println(brand + " goes at " + speed + " km/h");
    }
}

// Creating objects
Car c1 = new Car("Toyota", 120);
Car c2 = new Car("BMW", 200);

c1.displayInfo();  // Toyota goes at 120 km/h
c2.displayInfo();  // BMW goes at 200 km/h
```

---

## Encapsulation
Use **private** fields and **public** getters/setters.

```java
class Person {
    private String name;
    private int age;

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    public int getAge() { return age; }
    public void setAge(int age) {
        if (age > 0) this.age = age;
    }
}
```

---

## Inheritance
A **child class** extends a **parent class** and inherits its non-private members.

```java
class Animal {
    String name;
    void eat() { System.out.println(name + " is eating."); }
}

class Dog extends Animal {
    void bark() { System.out.println(name + " is barking!"); }
}

Dog d = new Dog();
d.name = "Buddy";
d.eat();   // inherited from Animal
d.bark();  // defined in Dog
```

### `super` keyword
```java
class Animal {
    Animal(String name) { System.out.println("Animal: " + name); }
}

class Dog extends Animal {
    Dog(String name) {
        super(name);   // call parent constructor
        System.out.println("Dog created.");
    }
}
```

---

## Polymorphism

### Method Overriding (Runtime Polymorphism)
```java
class Shape {
    void draw() { System.out.println("Drawing a shape"); }
}

class Circle extends Shape {
    @Override
    void draw() { System.out.println("Drawing a circle"); }
}

class Rectangle extends Shape {
    @Override
    void draw() { System.out.println("Drawing a rectangle"); }
}

Shape s = new Circle();
s.draw();   // Drawing a circle  (resolved at runtime)
```

---

## Abstraction

### Abstract Class
```java
abstract class Vehicle {
    abstract void start();   // no implementation

    void stop() {            // concrete method
        System.out.println("Vehicle stopped.");
    }
}

class Bike extends Vehicle {
    @Override
    void start() { System.out.println("Bike started."); }
}
```

### Interface
```java
interface Flyable {
    void fly();   // implicitly public abstract
}

class Bird implements Flyable {
    @Override
    public void fly() { System.out.println("Bird is flying."); }
}
```

| Feature          | Abstract Class          | Interface                  |
|------------------|-------------------------|----------------------------|
| Constructor      | Yes                     | No                         |
| Fields           | Any type                | `public static final` only |
| Multiple inherit | No (single parent)      | Yes (multiple interfaces)  |

---

## `static` Members
Belong to the **class**, not to individual objects.

```java
class Counter {
    static int count = 0;

    Counter() { count++; }

    static void showCount() {
        System.out.println("Objects created: " + count);
    }
}

new Counter(); new Counter(); new Counter();
Counter.showCount();  // Objects created: 3
```

---

## `this` Keyword
Refers to the **current object** inside instance methods/constructors.

```java
class Box {
    int width;
    Box(int width) {
        this.width = width;  // distinguishes field from parameter
    }
}
```
