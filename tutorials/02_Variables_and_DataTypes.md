# Tutorial 2: Variables and Data Types

## What are Variables?

Variables are containers that store data values. In Java, every variable must have a data type.

### Syntax:
```java
dataType variableName = value;
```

---

## Primitive Data Types

Java has 8 primitive data types:

### 1. Integer Types

#### byte
- Size: 8 bits
- Range: -128 to 127
```java
byte age = 25;
byte temperature = -10;
```

#### short
- Size: 16 bits
- Range: -32,768 to 32,767
```java
short year = 2024;
short elevation = -500;
```

#### int (Most commonly used)
- Size: 32 bits
- Range: -2,147,483,648 to 2,147,483,647
```java
int population = 1000000;
int salary = 75000;
```

#### long
- Size: 64 bits
- Range: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807
- Suffix with 'L'
```java
long distanceToSun = 149600000L;
long worldPopulation = 8000000000L;
```

### 2. Floating-Point Types

#### float
- Size: 32 bits
- Suffix with 'f'
```java
float price = 19.99f;
float temperature = 98.6f;
```

#### double (Most commonly used for decimals)
- Size: 64 bits
```java
double pi = 3.14159265359;
double salary = 75000.50;
```

### 3. Character Type

#### char
- Size: 16 bits
- Single character in single quotes
```java
char grade = 'A';
char symbol = '$';
char letter = 'z';
```

### 4. Boolean Type

#### boolean
- Size: 1 bit
- Values: true or false
```java
boolean isJavaFun = true;
boolean isRaining = false;
```

---

## Non-Primitive Data Types

### String
- Sequence of characters
- Not a primitive type (it's a class)
- Use double quotes

```java
String name = "John Doe";
String message = "Hello, World!";
String empty = "";
```

---

## Variable Declaration and Initialization

### Declaration (without value):
```java
int age;
String name;
boolean isActive;
```

### Initialization (assigning value):
```java
age = 25;
name = "Alice";
isActive = true;
```

### Declaration + Initialization:
```java
int age = 25;
String name = "Alice";
boolean isActive = true;
```

### Multiple variables of same type:
```java
int x = 5, y = 10, z = 15;
```

---

## Variable Naming Rules

### Valid Names:
```java
int age;
int myAge;
int _age;
int $age;
int age2;
```

### Invalid Names:
```java
int 2age;        // Cannot start with number
int my-age;      // Cannot use hyphen
int my age;      // Cannot have space
int int;         // Cannot use keywords
```

### Naming Conventions:
- Use camelCase: `myVariableName`
- Start with lowercase letter
- Use meaningful names: `studentAge` (not `sa`)
- Constants in UPPERCASE: `final int MAX_VALUE = 100;`

---

## Type Casting

### Implicit Casting (Automatic - Widening)
Smaller type to larger type:
```java
int myInt = 9;
double myDouble = myInt;  // int to double
System.out.println(myDouble);  // 9.0
```

### Explicit Casting (Manual - Narrowing)
Larger type to smaller type:
```java
double myDouble = 9.78;
int myInt = (int) myDouble;  // double to int
System.out.println(myInt);  // 9 (decimal part lost)
```

---

## Complete Example Program

```java
public class VariablesDemo {
    public static void main(String[] args) {
        // Integer types
        byte myByte = 100;
        short myShort = 5000;
        int myInt = 100000;
        long myLong = 15000000000L;

        // Floating-point types
        float myFloat = 5.99f;
        double myDouble = 19.99;

        // Character and Boolean
        char myChar = 'A';
        boolean myBoolean = true;

        // String
        String myString = "Hello Java";

        // Printing all variables
        System.out.println("Byte: " + myByte);
        System.out.println("Short: " + myShort);
        System.out.println("Int: " + myInt);
        System.out.println("Long: " + myLong);
        System.out.println("Float: " + myFloat);
        System.out.println("Double: " + myDouble);
        System.out.println("Char: " + myChar);
        System.out.println("Boolean: " + myBoolean);
        System.out.println("String: " + myString);
    }
}
```

---

## Exercises

### Exercise 1: Personal Information
Create variables to store and print:
- Your full name (String)
- Your age (int)
- Your height in meters (double)
- Your first initial (char)
- Whether you like programming (boolean)

### Exercise 2: Circle Calculator
```java
public class Circle {
    public static void main(String[] args) {
        double radius = 5.5;
        double pi = 3.14159;

        // Calculate and print:
        // 1. Area = pi * radius * radius
        // 2. Circumference = 2 * pi * radius
    }
}
```

### Exercise 3: Type Casting Practice
```java
public class CastingPractice {
    public static void main(String[] args) {
        // Convert these:
        int myInt = 10;
        // Convert to double and print

        double myDouble = 25.75;
        // Convert to int and print

        char myChar = '7';
        // Convert to int and print (ASCII value)
    }
}
```

### Exercise 4: Variable Swap
Swap the values of two variables without using a third variable:
```java
int a = 5;
int b = 10;
// Your code here to swap
System.out.println("a = " + a);  // Should print 10
System.out.println("b = " + b);  // Should print 5
```

---

## Common Mistakes to Avoid

1. **Forgetting to initialize variables**
   ```java
   int age;
   System.out.println(age);  // ERROR: variable might not be initialized
   ```

2. **Wrong suffix for long and float**
   ```java
   long big = 9999999999;    // ERROR: too large for int
   long big = 9999999999L;   // CORRECT

   float price = 19.99;      // ERROR: double cannot be converted to float
   float price = 19.99f;     // CORRECT
   ```

3. **Using reserved keywords as variable names**
   ```java
   int class = 5;  // ERROR
   int myClass = 5;  // CORRECT
   ```

---

## Key Takeaways

- Java is strongly typed - every variable must have a type
- Primitive types: byte, short, int, long, float, double, char, boolean
- String is not primitive, it's a class
- Use meaningful variable names
- Follow camelCase naming convention
- Always initialize variables before use
- Use appropriate data types to save memory

---

## Next Steps

Move to Tutorial 3: Operators to learn how to perform operations on variables.
