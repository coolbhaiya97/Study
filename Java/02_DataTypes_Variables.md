# 02 – Data Types & Variables

## Variables
A variable is a named container that stores a value.

```java
int age = 25;          // declaration + initialization
String name = "Java";
```

## Primitive Data Types (8 types)

| Type    | Size    | Default | Range / Description                      |
|---------|---------|---------|------------------------------------------|
| `byte`  | 1 byte  | 0       | -128 to 127                              |
| `short` | 2 bytes | 0       | -32,768 to 32,767                        |
| `int`   | 4 bytes | 0       | -2³¹ to 2³¹-1 (~2.1 billion)            |
| `long`  | 8 bytes | 0L      | -2⁶³ to 2⁶³-1                           |
| `float` | 4 bytes | 0.0f    | ~6-7 decimal digits of precision         |
| `double`| 8 bytes | 0.0d    | ~15 decimal digits of precision          |
| `char`  | 2 bytes | '\u0000'| Single Unicode character                 |
| `boolean`| 1 bit  | false   | `true` or `false`                        |

```java
byte   b  = 100;
short  s  = 30000;
int    i  = 123456;
long   l  = 9876543210L;   // suffix L required
float  f  = 3.14f;          // suffix f required
double d  = 3.14159265;
char   c  = 'A';
boolean flag = true;
```

## Non-Primitive (Reference) Types
- `String`, arrays, classes, interfaces, etc.
- Stored as references (pointers) to objects in heap memory.

```java
String greeting = "Hello, Java!";
int[]  numbers  = {1, 2, 3};
```

## Type Casting

### Widening (Implicit) – smaller → larger, no data loss
```java
int x = 10;
double y = x;   // automatically converts int to double
```

### Narrowing (Explicit) – larger → smaller, possible data loss
```java
double pi = 3.99;
int n = (int) pi;  // n = 3 (decimal part is truncated)
```

## Constants (`final`)
```java
final double PI = 3.14159;
// PI = 3.0;  // ERROR – cannot reassign a final variable
```

## Naming Rules
- Can use letters, digits, `_`, `$`
- Cannot start with a digit
- Case-sensitive (`age` ≠ `Age`)
- Cannot use Java reserved keywords

## Convention
| Kind      | Convention        | Example             |
|-----------|-------------------|---------------------|
| Variable  | camelCase         | `studentName`       |
| Constant  | UPPER_SNAKE_CASE  | `MAX_SIZE`          |
| Class     | PascalCase        | `BankAccount`       |
| Method    | camelCase         | `calculateSalary()` |
