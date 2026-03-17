# 01 – Introduction to Java

## What is Java?
- Java is a **high-level, object-oriented, platform-independent** programming language.
- Developed by **James Gosling** at Sun Microsystems in **1995**.
- Follows the principle: **"Write Once, Run Anywhere" (WORA)**.

## How Java Works
```
Source Code (.java)
      ↓  javac (compiler)
Bytecode (.class)
      ↓  JVM (Java Virtual Machine)
Machine Output
```

## Key Components
| Component | Description |
|-----------|-------------|
| **JDK** | Java Development Kit – for developers (includes JRE + compiler) |
| **JRE** | Java Runtime Environment – for running Java programs |
| **JVM** | Java Virtual Machine – executes bytecode on any platform |

## First Java Program

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### Breakdown
- `public class HelloWorld` – defines a class named `HelloWorld`
- `public static void main(String[] args)` – entry point of every Java program
- `System.out.println(...)` – prints text followed by a newline

## How to Compile and Run
```bash
javac HelloWorld.java   # compile
java HelloWorld         # run
```

## Java Features
- **Object-Oriented** – everything is an object
- **Platform Independent** – bytecode runs on any OS with JVM
- **Strongly Typed** – all variables must have a declared type
- **Automatic Memory Management** – Garbage Collector (GC) handles memory
- **Multithreading** – supports concurrent programming
- **Secure** – no pointer arithmetic; sandboxed execution
