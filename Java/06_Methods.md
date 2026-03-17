# 06 – Methods

## What is a Method?
A method is a **named block of code** that performs a specific task.
Using methods avoids repeating code (DRY – Don't Repeat Yourself).

## Syntax
```java
returnType methodName(parameterType paramName, ...) {
    // body
    return value; // only if returnType is not void
}
```

## Example
```java
public class Calculator {

    // Method that returns the sum of two integers
    static int add(int a, int b) {
        return a + b;
    }

    // Method with no return value (void)
    static void greet(String name) {
        System.out.println("Hello, " + name + "!");
    }

    public static void main(String[] args) {
        int result = add(5, 3);
        System.out.println("Sum = " + result);  // Sum = 8

        greet("Alice");                          // Hello, Alice!
    }
}
```

## Parameters vs Arguments
- **Parameters** – variables listed in the method definition.
- **Arguments** – actual values passed when calling the method.

```java
static void show(int x) { ... }  // x is a parameter
show(42);                         // 42 is an argument
```

## Method Overloading
Same method name, **different parameter lists**.

```java
static int multiply(int a, int b)            { return a * b; }
static double multiply(double a, double b)   { return a * b; }
static int multiply(int a, int b, int c)     { return a * b * c; }

// Java picks the correct version based on argument types/count.
```

## Recursion
A method that **calls itself**.

```java
static int factorial(int n) {
    if (n == 0) return 1;           // base case
    return n * factorial(n - 1);    // recursive case
}

System.out.println(factorial(5));   // 120
```

> Always ensure a **base case** exists to prevent infinite recursion (StackOverflowError).

## Variable Scope
- Variables declared **inside** a method are **local** – not accessible outside.
- **Parameters** are also local to the method.

```java
static void demo() {
    int localVar = 10;   // local variable
}
// System.out.println(localVar);  // ERROR – out of scope
```

## Pass by Value
Java passes **copies** of primitive values to methods.

```java
static void doubleIt(int x) {
    x = x * 2;   // only the local copy changes
}

int n = 5;
doubleIt(n);
System.out.println(n);  // still 5
```

> For **objects/arrays**, the reference is copied, but the object itself can be modified.
