# Tutorial 4: Input and Output in Java

## Output in Java

### 1. System.out.print()
Prints without newline.

```java
public class OutputDemo {
    public static void main(String[] args) {
        System.out.print("Hello ");
        System.out.print("World");
        // Output: Hello World
    }
}
```

### 2. System.out.println()
Prints with newline (most commonly used).

```java
System.out.println("First line");
System.out.println("Second line");
// Output:
// First line
// Second line
```

### 3. System.out.printf()
Formatted output (like C's printf).

```java
public class FormattedOutput {
    public static void main(String[] args) {
        String name = "Alice";
        int age = 25;
        double height = 5.6;

        // Format specifiers
        System.out.printf("Name: %s%n", name);
        System.out.printf("Age: %d%n", age);
        System.out.printf("Height: %.2f%n", height);

        // Combined
        System.out.printf("Name: %s, Age: %d, Height: %.2f%n",
                         name, age, height);
    }
}
```

### Common Format Specifiers:
| Specifier | Description | Example |
|-----------|-------------|---------|
| %s | String | "Hello" |
| %d | Integer | 42 |
| %f | Float/Double | 3.14 |
| %.2f | Float with 2 decimals | 3.14 |
| %c | Character | 'A' |
| %b | Boolean | true |
| %n | Newline | (new line) |

---

## Input in Java

### Using Scanner Class

Scanner is the most common way to read input from users.

### Step 1: Import Scanner
```java
import java.util.Scanner;
```

### Step 2: Create Scanner Object
```java
Scanner scanner = new Scanner(System.in);
```

### Step 3: Read Input
```java
// Read different types
String name = scanner.nextLine();      // Read full line
int age = scanner.nextInt();            // Read integer
double price = scanner.nextDouble();    // Read double
float weight = scanner.nextFloat();     // Read float
boolean flag = scanner.nextBoolean();   // Read boolean
char letter = scanner.next().charAt(0); // Read character
```

### Step 4: Close Scanner
```java
scanner.close();
```

---

## Complete Input Example

```java
import java.util.Scanner;

public class InputDemo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Reading String
        System.out.print("Enter your name: ");
        String name = scanner.nextLine();

        // Reading Integer
        System.out.print("Enter your age: ");
        int age = scanner.nextInt();

        // Reading Double
        System.out.print("Enter your height (in meters): ");
        double height = scanner.nextDouble();

        // Reading Character
        System.out.print("Enter your grade: ");
        char grade = scanner.next().charAt(0);

        // Output
        System.out.println("\n--- Your Information ---");
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Height: " + height + " meters");
        System.out.println("Grade: " + grade);

        scanner.close();
    }
}
```

---

## Scanner Methods

| Method | Description | Returns |
|--------|-------------|---------|
| nextLine() | Reads entire line | String |
| next() | Reads single word | String |
| nextInt() | Reads integer | int |
| nextDouble() | Reads double | double |
| nextFloat() | Reads float | float |
| nextLong() | Reads long | long |
| nextBoolean() | Reads boolean | boolean |
| nextByte() | Reads byte | byte |
| nextShort() | Reads short | short |

---

## Common Input Issues

### Issue 1: nextLine() after nextInt()

```java
Scanner scanner = new Scanner(System.in);

System.out.print("Enter age: ");
int age = scanner.nextInt();

System.out.print("Enter name: ");
String name = scanner.nextLine();  // This will be skipped!

scanner.close();
```

**Problem**: `nextInt()` doesn't consume the newline character.

**Solution**: Add an extra `nextLine()` to consume the newline:
```java
Scanner scanner = new Scanner(System.in);

System.out.print("Enter age: ");
int age = scanner.nextInt();
scanner.nextLine();  // Consume the newline

System.out.print("Enter name: ");
String name = scanner.nextLine();  // Now it works!

scanner.close();
```

### Issue 2: InputMismatchException

```java
Scanner scanner = new Scanner(System.in);

System.out.print("Enter age: ");
int age = scanner.nextInt();  // If user enters "abc", throws exception!

scanner.close();
```

**Solution**: Validate input (we'll cover this in exception handling).

---

## String Concatenation in Output

### Using + Operator
```java
String name = "John";
int age = 25;
System.out.println("Name: " + name + ", Age: " + age);
```

### Using String.format()
```java
String message = String.format("Name: %s, Age: %d", name, age);
System.out.println(message);
```

### Using StringBuilder (efficient for multiple concatenations)
```java
StringBuilder sb = new StringBuilder();
sb.append("Name: ").append(name);
sb.append(", Age: ").append(age);
System.out.println(sb.toString());
```

---

## Escape Sequences

Special characters in strings:

| Escape | Description | Example |
|--------|-------------|---------|
| \n | Newline | "Line1\nLine2" |
| \t | Tab | "Name:\tJohn" |
| \\ | Backslash | "C:\\Users" |
| \" | Double quote | "He said \"Hi\"" |
| \' | Single quote | 'It\'s mine' |
| \r | Carriage return | "Hello\rWorld" |

```java
public class EscapeDemo {
    public static void main(String[] args) {
        System.out.println("Line 1\nLine 2");
        System.out.println("Name:\tJohn");
        System.out.println("Path: C:\\Users\\Documents");
        System.out.println("He said \"Hello\"");
    }
}
```

---

## Practical Examples

### Example 1: Simple Calculator
```java
import java.util.Scanner;

public class SimpleCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter first number: ");
        double num1 = scanner.nextDouble();

        System.out.print("Enter second number: ");
        double num2 = scanner.nextDouble();

        double sum = num1 + num2;
        double difference = num1 - num2;
        double product = num1 * num2;
        double quotient = num1 / num2;

        System.out.println("\n--- Results ---");
        System.out.println("Sum: " + sum);
        System.out.println("Difference: " + difference);
        System.out.println("Product: " + product);
        System.out.println("Quotient: " + quotient);

        scanner.close();
    }
}
```

### Example 2: Area of Circle
```java
import java.util.Scanner;

public class CircleArea {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter radius: ");
        double radius = scanner.nextDouble();

        double area = Math.PI * radius * radius;
        double circumference = 2 * Math.PI * radius;

        System.out.printf("Area: %.2f%n", area);
        System.out.printf("Circumference: %.2f%n", circumference);

        scanner.close();
    }
}
```

### Example 3: Personal Profile
```java
import java.util.Scanner;

public class Profile {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("=== Create Your Profile ===");

        System.out.print("Full Name: ");
        String name = scanner.nextLine();

        System.out.print("Age: ");
        int age = scanner.nextInt();
        scanner.nextLine();  // Consume newline

        System.out.print("City: ");
        String city = scanner.nextLine();

        System.out.print("Favorite Color: ");
        String color = scanner.nextLine();

        System.out.println("\n=== Your Profile ===");
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("City: " + city);
        System.out.println("Favorite Color: " + color);

        scanner.close();
    }
}
```

---

## Exercises

### Exercise 1: Temperature Converter
Create a program that:
- Asks user for temperature in Celsius
- Converts to Fahrenheit: F = (C × 9/5) + 32
- Displays result with 2 decimal places

### Exercise 2: BMI Calculator
Create a program that:
- Asks for weight (kg) and height (meters)
- Calculates BMI: weight / (height × height)
- Displays result with message

### Exercise 3: Shopping Bill
Create a program that:
- Asks for product name and price (3 items)
- Calculates total
- Adds 10% tax
- Displays itemized bill

### Exercise 4: Student Info
Create a program that collects:
- Student name
- Roll number
- 3 subject marks
- Calculate and display average

### Exercise 5: Age Calculator
Create a program that:
- Asks for birth year
- Calculates age (use 2024 as current year)
- Displays age in years

---

## Key Takeaways

- Use `System.out.println()` for output
- Use `Scanner` class for input
- Import Scanner: `import java.util.Scanner;`
- Always close Scanner: `scanner.close();`
- Use `nextLine()` after `nextInt()` to consume newline
- Use format specifiers with `printf()` for formatted output
- Escape sequences like \n, \t for special characters

---

## Next Steps

Move to Tutorial 5: Control Flow (if-else, switch) to learn decision-making in Java.
