# Tutorial 3: Operators in Java

## What are Operators?

Operators are symbols that perform operations on variables and values.

---

## 1. Arithmetic Operators

Used to perform mathematical operations.

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| + | Addition | 5 + 3 | 8 |
| - | Subtraction | 5 - 3 | 2 |
| * | Multiplication | 5 * 3 | 15 |
| / | Division | 10 / 2 | 5 |
| % | Modulus (Remainder) | 10 % 3 | 1 |
| ++ | Increment | x++ | x = x + 1 |
| -- | Decrement | x-- | x = x - 1 |

### Example:
```java
public class ArithmeticDemo {
    public static void main(String[] args) {
        int a = 10;
        int b = 3;

        System.out.println("Addition: " + (a + b));        // 13
        System.out.println("Subtraction: " + (a - b));     // 7
        System.out.println("Multiplication: " + (a * b));  // 30
        System.out.println("Division: " + (a / b));        // 3
        System.out.println("Modulus: " + (a % b));         // 1

        // Increment and Decrement
        int x = 5;
        System.out.println("x++ = " + (x++));  // Prints 5, then x becomes 6
        System.out.println("x = " + x);         // Prints 6

        int y = 5;
        System.out.println("++y = " + (++y));  // y becomes 6, then prints 6
    }
}
```

### Important Notes:
- Integer division truncates decimals: `7 / 2 = 3` (not 3.5)
- For decimal result, use double: `7.0 / 2 = 3.5`
- `x++` (post-increment): use value first, then increment
- `++x` (pre-increment): increment first, then use value

---

## 2. Assignment Operators

Used to assign values to variables.

| Operator | Example | Same As |
|----------|---------|---------|
| = | x = 5 | x = 5 |
| += | x += 3 | x = x + 3 |
| -= | x -= 3 | x = x - 3 |
| *= | x *= 3 | x = x * 3 |
| /= | x /= 3 | x = x / 3 |
| %= | x %= 3 | x = x % 3 |

### Example:
```java
public class AssignmentDemo {
    public static void main(String[] args) {
        int x = 10;

        x += 5;  // x = x + 5
        System.out.println(x);  // 15

        x -= 3;  // x = x - 3
        System.out.println(x);  // 12

        x *= 2;  // x = x * 2
        System.out.println(x);  // 24

        x /= 4;  // x = x / 4
        System.out.println(x);  // 6

        x %= 4;  // x = x % 4
        System.out.println(x);  // 2
    }
}
```

---

## 3. Comparison (Relational) Operators

Used to compare two values. Returns `true` or `false`.

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| == | Equal to | 5 == 3 | false |
| != | Not equal | 5 != 3 | true |
| > | Greater than | 5 > 3 | true |
| < | Less than | 5 < 3 | false |
| >= | Greater than or equal | 5 >= 5 | true |
| <= | Less than or equal | 5 <= 3 | false |

### Example:
```java
public class ComparisonDemo {
    public static void main(String[] args) {
        int a = 5;
        int b = 3;

        System.out.println(a == b);  // false
        System.out.println(a != b);  // true
        System.out.println(a > b);   // true
        System.out.println(a < b);   // false
        System.out.println(a >= 5);  // true
        System.out.println(b <= 3);  // true
    }
}
```

---

## 4. Logical Operators

Used to combine boolean expressions.

| Operator | Name | Description | Example |
|----------|------|-------------|---------|
| && | Logical AND | Returns true if both are true | (x > 5 && x < 10) |
| \|\| | Logical OR | Returns true if one is true | (x > 5 \|\| x < 3) |
| ! | Logical NOT | Reverses the result | !(x > 5) |

### Truth Table:

| A | B | A && B | A \|\| B | !A |
|---|---|--------|----------|-----|
| true | true | true | true | false |
| true | false | false | true | false |
| false | true | false | true | true |
| false | false | false | false | true |

### Example:
```java
public class LogicalDemo {
    public static void main(String[] args) {
        int age = 25;
        boolean hasLicense = true;

        // AND - both conditions must be true
        if (age >= 18 && hasLicense) {
            System.out.println("Can drive");
        }

        // OR - at least one condition must be true
        int day = 6;
        if (day == 6 || day == 7) {
            System.out.println("Weekend!");
        }

        // NOT - reverses boolean value
        boolean isRaining = false;
        if (!isRaining) {
            System.out.println("Go outside");
        }
    }
}
```

---

## 5. Ternary Operator

Shorthand for if-else statement.

### Syntax:
```java
variable = (condition) ? expressionTrue : expressionFalse;
```

### Example:
```java
public class TernaryDemo {
    public static void main(String[] args) {
        int age = 20;

        // Long way (if-else)
        String result1;
        if (age >= 18) {
            result1 = "Adult";
        } else {
            result1 = "Minor";
        }

        // Short way (ternary)
        String result2 = (age >= 18) ? "Adult" : "Minor";

        System.out.println(result2);  // Adult

        // Another example
        int a = 10, b = 20;
        int max = (a > b) ? a : b;
        System.out.println("Maximum: " + max);  // 20
    }
}
```

---

## 6. Bitwise Operators (Advanced)

Operate on bits (binary representation).

| Operator | Name | Example |
|----------|------|---------|
| & | AND | 5 & 3 = 1 |
| \| | OR | 5 \| 3 = 7 |
| ^ | XOR | 5 ^ 3 = 6 |
| ~ | NOT | ~5 = -6 |
| << | Left shift | 5 << 1 = 10 |
| >> | Right shift | 5 >> 1 = 2 |

### Example:
```java
public class BitwiseDemo {
    public static void main(String[] args) {
        int a = 5;  // Binary: 0101
        int b = 3;  // Binary: 0011

        System.out.println(a & b);   // 1 (0001)
        System.out.println(a | b);   // 7 (0111)
        System.out.println(a ^ b);   // 6 (0110)
        System.out.println(~a);      // -6
        System.out.println(a << 1);  // 10 (left shift)
        System.out.println(a >> 1);  // 2 (right shift)
    }
}
```

---

## Operator Precedence

Order of operations (from highest to lowest):

1. Postfix: `x++`, `x--`
2. Unary: `++x`, `--x`, `!`, `~`
3. Multiplicative: `*`, `/`, `%`
4. Additive: `+`, `-`
5. Shift: `<<`, `>>`
6. Relational: `<`, `>`, `<=`, `>=`
7. Equality: `==`, `!=`
8. Bitwise AND: `&`
9. Bitwise XOR: `^`
10. Bitwise OR: `|`
11. Logical AND: `&&`
12. Logical OR: `||`
13. Ternary: `?:`
14. Assignment: `=`, `+=`, `-=`, etc.

### Example:
```java
int result = 5 + 3 * 2;  // 11, not 16 (multiplication first)
int result2 = (5 + 3) * 2;  // 16 (parentheses first)
```

---

## Exercises

### Exercise 1: Basic Calculator
Create a program that performs all arithmetic operations on two numbers:
```java
public class Calculator {
    public static void main(String[] args) {
        int num1 = 20;
        int num2 = 6;

        // Perform and print: addition, subtraction,
        // multiplication, division, and modulus
    }
}
```

### Exercise 2: Temperature Converter
Convert Celsius to Fahrenheit: F = (C * 9/5) + 32
```java
public class TempConverter {
    public static void main(String[] args) {
        double celsius = 25.0;
        // Calculate and print Fahrenheit
    }
}
```

### Exercise 3: Even or Odd
Use modulus operator to check if a number is even or odd:
```java
public class EvenOdd {
    public static void main(String[] args) {
        int number = 17;
        // Use ternary operator to print "Even" or "Odd"
    }
}
```

### Exercise 4: Logical Operations
```java
public class Eligibility {
    public static void main(String[] args) {
        int age = 22;
        boolean isStudent = true;
        boolean hasCitizenship = true;

        // Check if person is eligible for scholarship:
        // Must be 18-25 years old AND be a student AND have citizenship
        // Print the result
    }
}
```

### Exercise 5: Comparison Challenge
```java
public class Compare {
    public static void main(String[] args) {
        int a = 15;
        int b = 20;
        int c = 15;

        // Print:
        // 1. Is a equal to c?
        // 2. Is b greater than a?
        // 3. Is a not equal to b?
        // 4. Is a less than or equal to c?
    }
}
```

---

## Common Mistakes

1. **Using = instead of ==**
   ```java
   if (x = 5) { }  // ERROR: assignment, not comparison
   if (x == 5) { }  // CORRECT
   ```

2. **Integer division**
   ```java
   int result = 5 / 2;  // 2, not 2.5
   double result = 5.0 / 2;  // 2.5 CORRECT
   ```

3. **Confusion between && and &**
   ```java
   // && is logical AND (for booleans)
   // & is bitwise AND (for numbers)
   ```

---

## Key Takeaways

- Arithmetic operators: +, -, *, /, %
- Comparison operators return boolean values
- Logical operators combine conditions
- Ternary operator is shorthand for if-else
- Operator precedence matters (use parentheses)
- ++ and -- have prefix and postfix forms

---

## Next Steps

Move to Tutorial 4: Input and Output to learn how to interact with users.
