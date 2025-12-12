# Tutorial 5: Control Flow Statements

Control flow statements allow you to control the execution flow of your program.

---

## 1. if Statement

Executes code if condition is true.

### Syntax:
```java
if (condition) {
    // code to execute if condition is true
}
```

### Example:
```java
public class IfDemo {
    public static void main(String[] args) {
        int age = 20;

        if (age >= 18) {
            System.out.println("You are an adult");
        }

        int temperature = 30;
        if (temperature > 25) {
            System.out.println("It's hot outside");
        }
    }
}
```

---

## 2. if-else Statement

Executes one block if condition is true, another if false.

### Syntax:
```java
if (condition) {
    // code if condition is true
} else {
    // code if condition is false
}
```

### Example:
```java
public class IfElseDemo {
    public static void main(String[] args) {
        int number = 7;

        if (number % 2 == 0) {
            System.out.println(number + " is even");
        } else {
            System.out.println(number + " is odd");
        }

        int age = 16;
        if (age >= 18) {
            System.out.println("Can vote");
        } else {
            System.out.println("Cannot vote");
        }
    }
}
```

---

## 3. if-else-if Ladder

Tests multiple conditions.

### Syntax:
```java
if (condition1) {
    // code for condition1
} else if (condition2) {
    // code for condition2
} else if (condition3) {
    // code for condition3
} else {
    // code if all conditions are false
}
```

### Example:
```java
public class GradeCalculator {
    public static void main(String[] args) {
        int marks = 85;

        if (marks >= 90) {
            System.out.println("Grade: A+");
        } else if (marks >= 80) {
            System.out.println("Grade: A");
        } else if (marks >= 70) {
            System.out.println("Grade: B");
        } else if (marks >= 60) {
            System.out.println("Grade: C");
        } else if (marks >= 50) {
            System.out.println("Grade: D");
        } else {
            System.out.println("Grade: F");
        }
    }
}
```

---

## 4. Nested if Statements

if statement inside another if statement.

### Example:
```java
public class NestedIfDemo {
    public static void main(String[] args) {
        int age = 25;
        boolean hasLicense = true;

        if (age >= 18) {
            if (hasLicense) {
                System.out.println("You can drive");
            } else {
                System.out.println("You need a license");
            }
        } else {
            System.out.println("You are too young to drive");
        }
    }
}
```

### Example 2: Finding Largest of Three Numbers
```java
public class LargestNumber {
    public static void main(String[] args) {
        int a = 25, b = 30, c = 20;

        if (a >= b) {
            if (a >= c) {
                System.out.println(a + " is largest");
            } else {
                System.out.println(c + " is largest");
            }
        } else {
            if (b >= c) {
                System.out.println(b + " is largest");
            } else {
                System.out.println(c + " is largest");
            }
        }
    }
}
```

---

## 5. switch Statement

Tests a variable against multiple values.

### Syntax:
```java
switch (expression) {
    case value1:
        // code
        break;
    case value2:
        // code
        break;
    default:
        // code if no case matches
}
```

### Example 1: Day of Week
```java
public class DaySwitch {
    public static void main(String[] args) {
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
            case 4:
                System.out.println("Thursday");
                break;
            case 5:
                System.out.println("Friday");
                break;
            case 6:
                System.out.println("Saturday");
                break;
            case 7:
                System.out.println("Sunday");
                break;
            default:
                System.out.println("Invalid day");
        }
    }
}
```

### Example 2: Simple Calculator
```java
import java.util.Scanner;

public class Calculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter first number: ");
        double num1 = scanner.nextDouble();

        System.out.print("Enter operator (+, -, *, /): ");
        char operator = scanner.next().charAt(0);

        System.out.print("Enter second number: ");
        double num2 = scanner.nextDouble();

        double result;

        switch (operator) {
            case '+':
                result = num1 + num2;
                System.out.println("Result: " + result);
                break;
            case '-':
                result = num1 - num2;
                System.out.println("Result: " + result);
                break;
            case '*':
                result = num1 * num2;
                System.out.println("Result: " + result);
                break;
            case '/':
                if (num2 != 0) {
                    result = num1 / num2;
                    System.out.println("Result: " + result);
                } else {
                    System.out.println("Cannot divide by zero");
                }
                break;
            default:
                System.out.println("Invalid operator");
        }

        scanner.close();
    }
}
```

### Important: The break Statement

Without `break`, execution "falls through" to the next case:

```java
int day = 5;
switch (day) {
    case 5:
        System.out.println("Friday");
        // No break - falls through
    case 6:
        System.out.println("Saturday");
        // No break - falls through
    case 7:
        System.out.println("Sunday");
        break;
}
// Output:
// Friday
// Saturday
// Sunday
```

### Fall-through can be useful:
```java
public class VowelChecker {
    public static void main(String[] args) {
        char letter = 'e';

        switch (letter) {
            case 'a':
            case 'e':
            case 'i':
            case 'o':
            case 'u':
                System.out.println(letter + " is a vowel");
                break;
            default:
                System.out.println(letter + " is a consonant");
        }
    }
}
```

---

## switch with Strings (Java 7+)

```java
public class StringSwitch {
    public static void main(String[] args) {
        String fruit = "apple";

        switch (fruit) {
            case "apple":
                System.out.println("Apple - $2");
                break;
            case "banana":
                System.out.println("Banana - $1");
                break;
            case "orange":
                System.out.println("Orange - $3");
                break;
            default:
                System.out.println("Fruit not available");
        }
    }
}
```

---

## Practical Examples

### Example 1: Ticket Pricing
```java
import java.util.Scanner;

public class TicketPrice {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your age: ");
        int age = scanner.nextInt();

        int price;

        if (age < 5) {
            price = 0;  // Free for kids under 5
        } else if (age < 18) {
            price = 10;  // Child ticket
        } else if (age < 60) {
            price = 20;  // Adult ticket
        } else {
            price = 15;  // Senior discount
        }

        System.out.println("Ticket price: $" + price);

        scanner.close();
    }
}
```

### Example 2: BMI Category
```java
import java.util.Scanner;

public class BMICategory {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter weight (kg): ");
        double weight = scanner.nextDouble();

        System.out.print("Enter height (m): ");
        double height = scanner.nextDouble();

        double bmi = weight / (height * height);

        System.out.printf("Your BMI: %.2f%n", bmi);

        if (bmi < 18.5) {
            System.out.println("Category: Underweight");
        } else if (bmi < 25) {
            System.out.println("Category: Normal weight");
        } else if (bmi < 30) {
            System.out.println("Category: Overweight");
        } else {
            System.out.println("Category: Obese");
        }

        scanner.close();
    }
}
```

### Example 3: Login System
```java
import java.util.Scanner;

public class LoginSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String correctUsername = "admin";
        String correctPassword = "pass123";

        System.out.print("Enter username: ");
        String username = scanner.nextLine();

        System.out.print("Enter password: ");
        String password = scanner.nextLine();

        if (username.equals(correctUsername) && password.equals(correctPassword)) {
            System.out.println("Login successful!");
        } else if (!username.equals(correctUsername)) {
            System.out.println("Invalid username");
        } else {
            System.out.println("Invalid password");
        }

        scanner.close();
    }
}
```

---

## Exercises

### Exercise 1: Leap Year Checker
Create a program that checks if a year is a leap year:
- Divisible by 4 AND
- (Not divisible by 100 OR divisible by 400)

### Exercise 2: Electricity Bill Calculator
Calculate bill based on units consumed:
- 0-100 units: $0.50 per unit
- 101-200 units: $0.75 per unit
- 201-300 units: $1.20 per unit
- Above 300: $1.50 per unit

### Exercise 3: Grade with Pass/Fail
Input marks for 3 subjects:
- Calculate average
- Assign grade (A, B, C, D, F)
- Check if passed (average >= 40)

### Exercise 4: Menu-Driven Program
Create a menu:
1. Add two numbers
2. Subtract two numbers
3. Multiply two numbers
4. Divide two numbers
5. Exit

Use switch to handle user choice.

### Exercise 5: Triangle Validator
Input three sides of a triangle:
- Check if they can form a valid triangle
- If valid, determine type: Equilateral, Isosceles, or Scalene

---

## Common Mistakes

1. **Using = instead of ==**
   ```java
   if (x = 5) { }  // ERROR
   if (x == 5) { }  // CORRECT
   ```

2. **Missing braces with multiple statements**
   ```java
   if (x > 5)
       System.out.println("Greater");
       System.out.println("Done");  // Always executes!

   // CORRECT:
   if (x > 5) {
       System.out.println("Greater");
       System.out.println("Done");
   }
   ```

3. **Forgetting break in switch**
   ```java
   switch (day) {
       case 1:
           System.out.println("Monday");
           // Missing break - falls through!
       case 2:
           System.out.println("Tuesday");
           break;
   }
   ```

4. **Using == for String comparison**
   ```java
   String name = "John";
   if (name == "John") { }  // May not work as expected
   if (name.equals("John")) { }  // CORRECT
   ```

---

## Key Takeaways

- `if` statement for single condition
- `if-else` for two alternatives
- `if-else-if` for multiple conditions
- `switch` for testing against specific values
- Always use `break` in switch (unless fall-through is intended)
- Use `.equals()` for String comparison
- Curly braces recommended even for single statements

---

## Next Steps

Move to Tutorial 6: Loops to learn how to repeat code execution.
