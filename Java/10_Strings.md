# 10 – String Handling

## What is a String?
- A `String` in Java is an **object** (not a primitive) that represents a sequence of characters.
- Strings are **immutable** – once created, their value cannot be changed.

## Creating Strings
```java
// String literal (stored in String Pool)
String s1 = "Hello";

// Using new keyword (creates a new object in heap)
String s2 = new String("Hello");
```

## Common String Methods
```java
String s = "  Hello, Java!  ";

s.length()               // 16 – total characters
s.trim()                 // "Hello, Java!" – removes leading/trailing spaces
s.toUpperCase()          // "  HELLO, JAVA!  "
s.toLowerCase()          // "  hello, java!  "
s.charAt(7)              // 'J'
s.indexOf("Java")        // 9
s.contains("Java")       // true
s.startsWith("  Hello")  // true
s.endsWith("!  ")        // true
s.replace("Java", "World")  // "  Hello, World!  "
s.substring(7)           // "Java!  "
s.substring(7, 11)       // "Java"
s.isEmpty()              // false
s.equals("Hello")        // false (case-sensitive, also has spaces)
s.equalsIgnoreCase("hello, java!") // false (spaces still differ)
```

## String Comparison
```java
String a = "hello";
String b = "hello";
String c = new String("hello");

// == compares references, not content
System.out.println(a == b);          // true  (same pool object)
System.out.println(a == c);          // false (different object in heap)

// .equals() compares content
System.out.println(a.equals(c));     // true
System.out.println(a.equalsIgnoreCase("HELLO"));  // true
```

> **Always use `.equals()`** to compare string content, never `==`.

## String Concatenation
```java
String first = "Hello";
String second = "World";
String full = first + ", " + second + "!";  // "Hello, World!"

// concat() method
String full2 = first.concat(second);  // "HelloWorld"
```

## Splitting and Joining
```java
String csv = "Alice,Bob,Charlie";
String[] names = csv.split(",");
System.out.println(names[0]);  // Alice
System.out.println(names.length);  // 3

String joined = String.join(" | ", names);
System.out.println(joined);  // Alice | Bob | Charlie
```

## String to Number and Back
```java
// String → int
int num = Integer.parseInt("42");

// String → double
double d = Double.parseDouble("3.14");

// Number → String
String s = String.valueOf(100);
String s2 = Integer.toString(200);
String s3 = "" + 300;   // implicit conversion via concatenation
```

## StringBuilder (Mutable)
When you need to modify strings frequently, use `StringBuilder` for better performance.

```java
StringBuilder sb = new StringBuilder();
sb.append("Hello");
sb.append(", ");
sb.append("World");
sb.insert(5, "!!");       // "Hello!!, World"
sb.delete(5, 7);          // "Hello, World"
sb.reverse();             // "dlroW ,olleH"

String result = sb.toString();
System.out.println(result);  // dlroW ,olleH
```

| Feature    | `String`     | `StringBuilder` |
|------------|--------------|-----------------|
| Mutability | Immutable    | Mutable         |
| Thread-safe| Yes          | No              |
| Performance| Slower (concat)| Faster for modification |

## Useful String Formatting
```java
String name = "Alice";
int age = 25;

// String.format()
String msg = String.format("Name: %s, Age: %d", name, age);
System.out.println(msg);  // Name: Alice, Age: 25

// printf()
System.out.printf("%-10s %5d%n", name, age);
```

### Format Specifiers
| Specifier | Type    |
|-----------|---------|
| `%s`      | String  |
| `%d`      | Integer |
| `%f`      | Float/Double |
| `%c`      | Char    |
| `%b`      | Boolean |
| `%n`      | Newline |
