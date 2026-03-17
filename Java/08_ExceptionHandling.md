# 08 – Exception Handling

## What is an Exception?
An **exception** is an unexpected event that disrupts the normal flow of a program
(e.g., dividing by zero, accessing a null object, invalid array index).

## Exception Hierarchy
```
Throwable
├── Error              (serious, usually unrecoverable – e.g., OutOfMemoryError)
└── Exception
    ├── RuntimeException  (unchecked – e.g., NullPointerException, ArrayIndexOutOfBoundsException)
    └── IOException       (checked – must be handled at compile time)
```

## try-catch-finally
```java
try {
    int result = 10 / 0;            // throws ArithmeticException
} catch (ArithmeticException e) {
    System.out.println("Error: " + e.getMessage());  // / by zero
} finally {
    System.out.println("This always runs.");
}
```
- **try** – code that might throw an exception
- **catch** – handles the exception
- **finally** – always executes (good for cleanup like closing files)

## Multiple catch Blocks
```java
try {
    int[] arr = new int[3];
    arr[5] = 10;                          // ArrayIndexOutOfBoundsException
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array error: " + e.getMessage());
} catch (Exception e) {
    System.out.println("General error: " + e.getMessage());
}
```
> Always put more **specific** exceptions before more **general** ones.

## throw vs throws
```java
// throw – manually throw an exception
static void checkAge(int age) {
    if (age < 18) {
        throw new IllegalArgumentException("Age must be 18+");
    }
}

// throws – declare that a method may throw a checked exception
static void readFile(String path) throws IOException {
    // ... file reading code
}
```

## Common Built-in Exceptions
| Exception                        | Cause                                |
|----------------------------------|--------------------------------------|
| `NullPointerException`           | Using a null reference               |
| `ArrayIndexOutOfBoundsException` | Accessing invalid array index        |
| `ClassCastException`             | Invalid type cast                    |
| `ArithmeticException`            | Division by zero                     |
| `NumberFormatException`          | Parsing invalid number string        |
| `StackOverflowError`             | Infinite recursion                   |
| `IOException`                    | File/IO operation failed             |

## Custom Exceptions
```java
class InsufficientFundsException extends Exception {
    InsufficientFundsException(String message) {
        super(message);
    }
}

class BankAccount {
    double balance = 100.0;

    void withdraw(double amount) throws InsufficientFundsException {
        if (amount > balance) {
            throw new InsufficientFundsException("Not enough funds!");
        }
        balance -= amount;
    }
}
```

## try-with-resources (Java 7+)
Automatically closes resources (implements `AutoCloseable`).
```java
try (FileReader fr = new FileReader("file.txt")) {
    // use fr
} catch (IOException e) {
    e.printStackTrace();
}
// fr is automatically closed after this block
```
