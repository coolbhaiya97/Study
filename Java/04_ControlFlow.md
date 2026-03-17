# 04 – Control Flow

## if / else if / else
```java
int marks = 75;

if (marks >= 90) {
    System.out.println("Grade: A");
} else if (marks >= 75) {
    System.out.println("Grade: B");
} else if (marks >= 60) {
    System.out.println("Grade: C");
} else {
    System.out.println("Grade: F");
}
```

## switch Statement
```java
int day = 3;

switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    case 3:
        System.out.println("Wednesday");
        break;
    default:
        System.out.println("Other day");
}
```
> **Important:** Always use `break` to prevent fall-through to the next case.
> `switch` works with `int`, `char`, `String`, and `enum`.

## for Loop
```java
for (int i = 0; i < 5; i++) {
    System.out.println("i = " + i);
}
// prints 0, 1, 2, 3, 4
```

## while Loop
```java
int count = 0;
while (count < 5) {
    System.out.println("count = " + count);
    count++;
}
```

## do-while Loop
```java
int n = 0;
do {
    System.out.println("n = " + n);
    n++;
} while (n < 5);
// Executes the body AT LEAST ONCE before checking the condition.
```

## Enhanced for Loop (for-each)
```java
int[] numbers = {10, 20, 30, 40};

for (int num : numbers) {
    System.out.println(num);
}
```

## break and continue
```java
// break – exits the loop immediately
for (int i = 0; i < 10; i++) {
    if (i == 5) break;
    System.out.println(i);   // prints 0 to 4
}

// continue – skips the current iteration
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) continue;
    System.out.println(i);   // prints odd numbers: 1,3,5,7,9
}
```

## Nested Loops Example – Multiplication Table
```java
for (int i = 1; i <= 5; i++) {
    for (int j = 1; j <= 5; j++) {
        System.out.print(i * j + "\t");
    }
    System.out.println();
}
```
