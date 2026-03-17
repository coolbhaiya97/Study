# 03 – Operators

## Arithmetic Operators
| Operator | Description        | Example       | Result |
|----------|--------------------|---------------|--------|
| `+`      | Addition           | `5 + 3`       | `8`    |
| `-`      | Subtraction        | `5 - 3`       | `2`    |
| `*`      | Multiplication     | `5 * 3`       | `15`   |
| `/`      | Division           | `5 / 2`       | `2` (integer division) |
| `%`      | Modulus (remainder)| `5 % 2`       | `1`    |

> **Integer Division:** `5 / 2 = 2` (not 2.5). Use `5.0 / 2` or cast to get a decimal.

## Assignment Operators
```java
int x = 10;
x += 5;   // x = x + 5  → 15
x -= 3;   // x = x - 3  → 12
x *= 2;   // x = x * 2  → 24
x /= 4;   // x = x / 4  → 6
x %= 4;   // x = x % 4  → 2
```

## Comparison (Relational) Operators
| Operator | Meaning                  | Example   | Result  |
|----------|--------------------------|-----------|---------|
| `==`     | Equal to                 | `5 == 5`  | `true`  |
| `!=`     | Not equal to             | `5 != 3`  | `true`  |
| `>`      | Greater than             | `5 > 3`   | `true`  |
| `<`      | Less than                | `5 < 3`   | `false` |
| `>=`     | Greater than or equal to | `5 >= 5`  | `true`  |
| `<=`     | Less than or equal to    | `5 <= 4`  | `false` |

## Logical Operators
| Operator | Meaning | Example              | Result |
|----------|---------|----------------------|--------|
| `&&`     | AND     | `true && false`      | `false`|
| `\|\|`   | OR      | `true \|\| false`    | `true` |
| `!`      | NOT     | `!true`              | `false`|

```java
int age = 20;
boolean isAdult = (age >= 18) && (age < 60);  // true
```

## Increment & Decrement
```java
int a = 5;
a++;   // post-increment: use a (5), then increment → a = 6
++a;   // pre-increment:  increment first → a = 7, then use
a--;   // post-decrement
--a;   // pre-decrement
```

## Ternary Operator
```java
int max = (a > b) ? a : b;
// equivalent to: if (a > b) max = a; else max = b;
```

## Bitwise Operators (brief overview)
| Operator | Description  |
|----------|--------------|
| `&`      | Bitwise AND  |
| `\|`     | Bitwise OR   |
| `^`      | Bitwise XOR  |
| `~`      | Bitwise NOT  |
| `<<`     | Left shift   |
| `>>`     | Right shift  |

## Operator Precedence (high → low)
1. `()` – parentheses
2. `++` `--` (unary), `!` `~`
3. `*` `/` `%`
4. `+` `-`
5. `<` `<=` `>` `>=`
6. `==` `!=`
7. `&&`
8. `||`
9. `=` `+=` `-=` etc.
