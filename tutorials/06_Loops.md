# Tutorial 6: Loops in Java

Loops are used to execute a block of code repeatedly.

---

## 1. while Loop

Executes code while condition is true.

### Syntax:
```java
while (condition) {
    // code to execute
}
```

### Example:
```java
public class WhileDemo {
    public static void main(String[] args) {
        // Print numbers 1 to 5
        int i = 1;
        while (i <= 5) {
            System.out.println(i);
            i++;
        }

        // Sum of first 10 numbers
        int num = 1;
        int sum = 0;
        while (num <= 10) {
            sum += num;
            num++;
        }
        System.out.println("Sum: " + sum);  // 55
    }
}
```

---

## 2. do-while Loop

Executes code at least once, then checks condition.

### Syntax:
```java
do {
    // code to execute
} while (condition);
```

### Example:
```java
public class DoWhileDemo {
    public static void main(String[] args) {
        int i = 1;
        do {
            System.out.println(i);
            i++;
        } while (i <= 5);

        // Executes at least once even if condition is false
        int x = 10;
        do {
            System.out.println("Executed once: " + x);
        } while (x < 5);  // Condition is false but runs once
    }
}
```

### Difference: while vs do-while
```java
// while - may not execute at all
int a = 10;
while (a < 5) {
    System.out.println("while: " + a);  // Never executes
}

// do-while - executes at least once
int b = 10;
do {
    System.out.println("do-while: " + b);  // Executes once
} while (b < 5);
```

---

## 3. for Loop

Most commonly used loop with counter.

### Syntax:
```java
for (initialization; condition; update) {
    // code to execute
}
```

### Example:
```java
public class ForDemo {
    public static void main(String[] args) {
        // Print numbers 1 to 5
        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
        }

        // Print even numbers from 2 to 10
        for (int i = 2; i <= 10; i += 2) {
            System.out.println(i);
        }

        // Count backwards
        for (int i = 10; i >= 1; i--) {
            System.out.println(i);
        }

        // Multiple variables
        for (int i = 0, j = 10; i < j; i++, j--) {
            System.out.println("i = " + i + ", j = " + j);
        }
    }
}
```

---

## 4. Enhanced for Loop (for-each)

Used to iterate through arrays and collections.

### Syntax:
```java
for (dataType variable : array/collection) {
    // code to execute
}
```

### Example:
```java
public class ForEachDemo {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        // Traditional for loop
        for (int i = 0; i < numbers.length; i++) {
            System.out.println(numbers[i]);
        }

        // Enhanced for loop (easier)
        for (int num : numbers) {
            System.out.println(num);
        }

        // With strings
        String[] fruits = {"Apple", "Banana", "Orange"};
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

---

## 5. Nested Loops

Loop inside another loop.

### Example 1: Multiplication Table
```java
public class MultiplicationTable {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= 10; j++) {
                System.out.print(i * j + "\t");
            }
            System.out.println();
        }
    }
}
```

### Example 2: Pattern Printing
```java
public class PatternDemo {
    public static void main(String[] args) {
        // Right triangle
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
        // Output:
        // *
        // * *
        // * * *
        // * * * *
        // * * * * *
    }
}
```

---

## 6. break Statement

Exits the loop immediately.

### Example:
```java
public class BreakDemo {
    public static void main(String[] args) {
        // Stop when i equals 5
        for (int i = 1; i <= 10; i++) {
            if (i == 5) {
                break;
            }
            System.out.println(i);
        }
        // Output: 1 2 3 4

        // Find first number divisible by 7
        for (int i = 1; i <= 100; i++) {
            if (i % 7 == 0) {
                System.out.println("First number: " + i);
                break;
            }
        }
    }
}
```

---

## 7. continue Statement

Skips current iteration and continues with next.

### Example:
```java
public class ContinueDemo {
    public static void main(String[] args) {
        // Skip number 5
        for (int i = 1; i <= 10; i++) {
            if (i == 5) {
                continue;
            }
            System.out.println(i);
        }
        // Output: 1 2 3 4 6 7 8 9 10

        // Print only odd numbers
        for (int i = 1; i <= 10; i++) {
            if (i % 2 == 0) {
                continue;  // Skip even numbers
            }
            System.out.println(i);
        }
    }
}
```

---

## Practical Examples

### Example 1: Factorial Calculator
```java
import java.util.Scanner;

public class Factorial {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int n = scanner.nextInt();

        long factorial = 1;
        for (int i = 1; i <= n; i++) {
            factorial *= i;
        }

        System.out.println("Factorial of " + n + " = " + factorial);

        scanner.close();
    }
}
```

### Example 2: Sum and Average
```java
import java.util.Scanner;

public class SumAverage {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("How many numbers? ");
        int count = scanner.nextInt();

        int sum = 0;
        for (int i = 1; i <= count; i++) {
            System.out.print("Enter number " + i + ": ");
            int num = scanner.nextInt();
            sum += num;
        }

        double average = (double) sum / count;

        System.out.println("Sum: " + sum);
        System.out.println("Average: " + average);

        scanner.close();
    }
}
```

### Example 3: Prime Number Checker
```java
import java.util.Scanner;

public class PrimeChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int num = scanner.nextInt();

        boolean isPrime = true;

        if (num <= 1) {
            isPrime = false;
        } else {
            for (int i = 2; i <= num / 2; i++) {
                if (num % i == 0) {
                    isPrime = false;
                    break;
                }
            }
        }

        if (isPrime) {
            System.out.println(num + " is prime");
        } else {
            System.out.println(num + " is not prime");
        }

        scanner.close();
    }
}
```

### Example 4: Number Guessing Game
```java
import java.util.Scanner;
import java.util.Random;

public class GuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int secretNumber = random.nextInt(100) + 1;
        int guess;
        int attempts = 0;

        System.out.println("Guess the number (1-100)!");

        do {
            System.out.print("Enter your guess: ");
            guess = scanner.nextInt();
            attempts++;

            if (guess < secretNumber) {
                System.out.println("Too low!");
            } else if (guess > secretNumber) {
                System.out.println("Too high!");
            } else {
                System.out.println("Correct! You guessed in " + attempts + " attempts");
            }
        } while (guess != secretNumber);

        scanner.close();
    }
}
```

### Example 5: Fibonacci Series
```java
import java.util.Scanner;

public class Fibonacci {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("How many terms? ");
        int n = scanner.nextInt();

        int first = 0, second = 1;

        System.out.print("Fibonacci Series: " + first + " " + second);

        for (int i = 3; i <= n; i++) {
            int next = first + second;
            System.out.print(" " + next);
            first = second;
            second = next;
        }

        scanner.close();
    }
}
```

---

## Pattern Printing Examples

### Pattern 1: Square
```java
for (int i = 1; i <= 5; i++) {
    for (int j = 1; j <= 5; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
// * * * * *
// * * * * *
// * * * * *
// * * * * *
// * * * * *
```

### Pattern 2: Right Triangle
```java
for (int i = 1; i <= 5; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
// *
// * *
// * * *
// * * * *
// * * * * *
```

### Pattern 3: Inverted Triangle
```java
for (int i = 5; i >= 1; i--) {
    for (int j = 1; j <= i; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
// * * * * *
// * * * *
// * * *
// * *
// *
```

### Pattern 4: Pyramid
```java
for (int i = 1; i <= 5; i++) {
    // Print spaces
    for (int j = 1; j <= 5 - i; j++) {
        System.out.print(" ");
    }
    // Print stars
    for (int k = 1; k <= i; k++) {
        System.out.print("* ");
    }
    System.out.println();
}
//     *
//    * *
//   * * *
//  * * * *
// * * * * *
```

---

## Exercises

### Exercise 1: Reverse a Number
Input: 12345
Output: 54321

### Exercise 2: Palindrome Checker
Check if a number reads the same forwards and backwards.
Example: 121 is a palindrome, 123 is not.

### Exercise 3: Print all Prime Numbers
Print all prime numbers between 1 and 100.

### Exercise 4: Armstrong Number
Check if a number is an Armstrong number.
Example: 153 = 1³ + 5³ + 3³ = 1 + 125 + 27 = 153

### Exercise 5: Menu-Driven Calculator
Create a calculator that keeps running until user chooses to exit:
1. Add
2. Subtract
3. Multiply
4. Divide
5. Exit

### Exercise 6: Pattern Challenge
Print this pattern:
```
    1
   2 2
  3 3 3
 4 4 4 4
5 5 5 5 5
```

---

## Common Mistakes

1. **Infinite loop - forgetting to update counter**
   ```java
   int i = 1;
   while (i <= 5) {
       System.out.println(i);
       // Forgot i++; - infinite loop!
   }
   ```

2. **Off-by-one error**
   ```java
   for (int i = 0; i <= 10; i++) {  // Runs 11 times, not 10
       System.out.println(i);
   }
   ```

3. **Wrong loop condition**
   ```java
   for (int i = 1; i < 5; i++) {  // Prints 1-4, not 1-5
       System.out.println(i);
   }
   ```

4. **Modifying loop variable incorrectly**
   ```java
   for (int i = 0; i < 10; i++) {
       i++;  // Don't do this! i increments twice
   }
   ```

---

## Choosing the Right Loop

- **for loop**: When you know how many iterations
- **while loop**: When condition-based, unknown iterations
- **do-while**: When you need at least one execution
- **for-each**: When iterating through arrays/collections

---

## Key Takeaways

- Loops repeat code execution
- `for` loop: known iterations
- `while` loop: condition-based
- `do-while`: executes at least once
- `for-each`: iterate arrays/collections
- `break`: exit loop
- `continue`: skip iteration
- Watch out for infinite loops

---

## Next Steps

Move to Tutorial 7: Arrays to learn how to store multiple values.
