# Tutorial 8: Introduction to Object-Oriented Programming (OOP)

## What is OOP?

Object-Oriented Programming is a programming paradigm based on the concept of "objects" that contain data (attributes) and code (methods).

---

## Why OOP?

- **Modularity**: Code is organized into reusable objects
- **Reusability**: Create once, use many times
- **Maintainability**: Easy to update and maintain
- **Security**: Data hiding through encapsulation
- **Real-world modeling**: Represents real-world entities

---

## 1. Classes and Objects

### Class
A blueprint or template for creating objects.

### Object
An instance of a class with actual values.

### Analogy:
- **Class**: Car blueprint (design)
- **Object**: Actual cars (Honda Civic, Tesla Model 3)

---

## Creating a Class

### Syntax:
```java
class ClassName {
    // Attributes (fields/variables)
    // Methods (functions)
}
```

### Example 1: Simple Student Class
```java
class Student {
    // Attributes
    String name;
    int age;
    int rollNumber;

    // Method
    void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Roll Number: " + rollNumber);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating object
        Student student1 = new Student();

        // Setting values
        student1.name = "Alice";
        student1.age = 20;
        student1.rollNumber = 101;

        // Calling method
        student1.displayInfo();
    }
}
```

### Output:
```
Name: Alice
Age: 20
Roll Number: 101
```

---

## 2. Constructors

Special methods called when an object is created.

### Characteristics:
- Same name as class
- No return type
- Automatically called when object is created

### Types of Constructors:

#### Default Constructor:
```java
class Student {
    String name;
    int age;

    // Default constructor
    Student() {
        name = "Unknown";
        age = 0;
    }
}
```

#### Parameterized Constructor:
```java
class Student {
    String name;
    int age;

    // Parameterized constructor
    Student(String n, int a) {
        name = n;
        age = a;
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Alice", 20);
        Student s2 = new Student("Bob", 22);
    }
}
```

#### Constructor Overloading:
```java
class Student {
    String name;
    int age;
    int rollNumber;

    // Constructor 1
    Student() {
        name = "Unknown";
        age = 0;
        rollNumber = 0;
    }

    // Constructor 2
    Student(String n, int a) {
        name = n;
        age = a;
        rollNumber = 0;
    }

    // Constructor 3
    Student(String n, int a, int r) {
        name = n;
        age = a;
        rollNumber = r;
    }
}
```

---

## 3. Methods

Functions defined inside a class.

### Example:
```java
class Calculator {
    // Method without parameters
    void welcome() {
        System.out.println("Welcome to Calculator");
    }

    // Method with parameters
    int add(int a, int b) {
        return a + b;
    }

    // Method with multiple parameters
    double calculateArea(double length, double width) {
        return length * width;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();

        calc.welcome();
        int sum = calc.add(5, 3);
        System.out.println("Sum: " + sum);

        double area = calc.calculateArea(5.5, 3.2);
        System.out.println("Area: " + area);
    }
}
```

---

## 4. The 'this' Keyword

Refers to the current object.

### Uses:
1. Distinguish between instance variables and parameters
2. Call other constructors
3. Pass current object as parameter

### Example:
```java
class Student {
    String name;
    int age;

    // Using 'this' to distinguish
    Student(String name, int age) {
        this.name = name;  // this.name refers to instance variable
        this.age = age;    // name refers to parameter
    }

    void display() {
        System.out.println("Name: " + this.name);
        System.out.println("Age: " + this.age);
    }
}
```

---

## 5. Static Members

Belong to the class, not to objects.

### Static Variable:
```java
class Student {
    String name;
    static String schoolName = "ABC School";  // Shared by all students

    Student(String name) {
        this.name = name;
    }

    void display() {
        System.out.println("Name: " + name);
        System.out.println("School: " + schoolName);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Alice");
        Student s2 = new Student("Bob");

        s1.display();
        s2.display();

        // Access static variable using class name
        System.out.println(Student.schoolName);
    }
}
```

### Static Method:
```java
class MathUtils {
    // Static method - can be called without creating object
    static int square(int n) {
        return n * n;
    }

    static int cube(int n) {
        return n * n * n;
    }
}

public class Main {
    public static void main(String[] args) {
        // Call without creating object
        int result = MathUtils.square(5);
        System.out.println("Square: " + result);

        System.out.println("Cube: " + MathUtils.cube(3));
    }
}
```

---

## Practical Examples

### Example 1: Bank Account Class
```java
class BankAccount {
    String accountNumber;
    String holderName;
    double balance;

    // Constructor
    BankAccount(String accountNumber, String holderName, double initialBalance) {
        this.accountNumber = accountNumber;
        this.holderName = holderName;
        this.balance = initialBalance;
    }

    // Deposit method
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: $" + amount);
            System.out.println("New balance: $" + balance);
        } else {
            System.out.println("Invalid amount");
        }
    }

    // Withdraw method
    void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawn: $" + amount);
            System.out.println("New balance: $" + balance);
        } else {
            System.out.println("Insufficient funds or invalid amount");
        }
    }

    // Display account info
    void displayInfo() {
        System.out.println("Account Number: " + accountNumber);
        System.out.println("Holder Name: " + holderName);
        System.out.println("Balance: $" + balance);
    }
}

public class Main {
    public static void main(String[] args) {
        BankAccount account = new BankAccount("123456", "John Doe", 1000.0);

        account.displayInfo();
        account.deposit(500);
        account.withdraw(200);
        account.displayInfo();
    }
}
```

### Example 2: Rectangle Class
```java
class Rectangle {
    double length;
    double width;

    // Constructor
    Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    // Calculate area
    double calculateArea() {
        return length * width;
    }

    // Calculate perimeter
    double calculatePerimeter() {
        return 2 * (length + width);
    }

    // Display details
    void display() {
        System.out.println("Length: " + length);
        System.out.println("Width: " + width);
        System.out.println("Area: " + calculateArea());
        System.out.println("Perimeter: " + calculatePerimeter());
    }
}

public class Main {
    public static void main(String[] args) {
        Rectangle rect1 = new Rectangle(5.0, 3.0);
        Rectangle rect2 = new Rectangle(7.5, 4.2);

        System.out.println("Rectangle 1:");
        rect1.display();

        System.out.println("\nRectangle 2:");
        rect2.display();
    }
}
```

### Example 3: Book Library System
```java
class Book {
    String title;
    String author;
    String isbn;
    boolean isAvailable;

    // Constructor
    Book(String title, String author, String isbn) {
        this.title = title;
        this.author = author;
        this.isbn = isbn;
        this.isAvailable = true;
    }

    // Borrow book
    void borrowBook() {
        if (isAvailable) {
            isAvailable = false;
            System.out.println("Book borrowed: " + title);
        } else {
            System.out.println("Book not available");
        }
    }

    // Return book
    void returnBook() {
        isAvailable = true;
        System.out.println("Book returned: " + title);
    }

    // Display book info
    void displayInfo() {
        System.out.println("Title: " + title);
        System.out.println("Author: " + author);
        System.out.println("ISBN: " + isbn);
        System.out.println("Available: " + (isAvailable ? "Yes" : "No"));
    }
}

public class Main {
    public static void main(String[] args) {
        Book book1 = new Book("Java Programming", "John Smith", "ISBN123");
        Book book2 = new Book("Data Structures", "Jane Doe", "ISBN456");

        book1.displayInfo();
        book1.borrowBook();
        book1.displayInfo();
        book1.returnBook();
    }
}
```

---

## Exercises

### Exercise 1: Employee Class
Create an Employee class with:
- Attributes: name, id, salary
- Methods: display info, give raise (increase salary by percentage)

### Exercise 2: Circle Class
Create a Circle class with:
- Attribute: radius
- Methods: calculate area, calculate circumference

### Exercise 3: Car Class
Create a Car class with:
- Attributes: brand, model, year, speed
- Methods: accelerate, brake, display info

### Exercise 4: Student Grade System
Create a Student class with:
- Attributes: name, marks in 3 subjects
- Methods: calculate average, display grade

### Exercise 5: Counter Class
Create a Counter class with:
- Static variable to keep track of total count
- Methods: increment, decrement, display count

---

## Key Concepts Summary

### Class vs Object
- **Class**: Blueprint/Template
- **Object**: Instance with actual values

### Constructor
- Special method for initialization
- Same name as class
- No return type

### 'this' Keyword
- Refers to current object
- Used to distinguish between instance variables and parameters

### Static
- Belongs to class, not objects
- Shared by all objects
- Access using class name

---

## Four Pillars of OOP (Preview)

1. **Encapsulation**: Data hiding (covered in next tutorial)
2. **Inheritance**: Reusing code from parent classes
3. **Polymorphism**: One interface, multiple implementations
4. **Abstraction**: Hiding complex implementation details

---

## Best Practices

1. Use meaningful class and variable names
2. One class per file (for public classes)
3. Keep methods short and focused
4. Use constructors for initialization
5. Follow naming conventions:
   - Classes: PascalCase (Student, BankAccount)
   - Methods/Variables: camelCase (displayInfo, studentName)

---

## Common Mistakes

1. **Forgetting 'new' keyword**
   ```java
   Student s = Student();  // ERROR
   Student s = new Student();  // CORRECT
   ```

2. **Accessing instance members without object**
   ```java
   class Student {
       String name;
   }
   System.out.println(Student.name);  // ERROR
   ```

3. **Static method accessing instance variable**
   ```java
   class Test {
       int x = 10;
       static void display() {
           System.out.println(x);  // ERROR
       }
   }
   ```

---

## Next Steps

- Learn about Encapsulation and Access Modifiers
- Study Inheritance
- Explore Polymorphism
- Understand Abstract Classes and Interfaces

Continue to advanced OOP tutorials to master Java!
