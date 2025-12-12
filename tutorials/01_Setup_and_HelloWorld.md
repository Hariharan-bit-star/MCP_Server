# Tutorial 1: Setting Up Java and Your First Program

## Part 1: Installing Java Development Kit (JDK)

### For Windows:
1. Go to [Oracle JDK Downloads](https://www.oracle.com/java/technologies/downloads/)
2. Download the latest JDK version for Windows
3. Run the installer and follow the prompts
4. Set up Environment Variables:
   - Right-click "This PC" → Properties → Advanced System Settings
   - Click "Environment Variables"
   - Add JAVA_HOME: `C:\Program Files\Java\jdk-XX`
   - Add to PATH: `%JAVA_HOME%\bin`

### For Mac:
```bash
# Using Homebrew
brew install openjdk@17

# Or download from Oracle website
```

### For Linux:
```bash
# Ubuntu/Debian
sudo apt update
sudo apt install openjdk-17-jdk

# Fedora
sudo dnf install java-17-openjdk
```

### Verify Installation:
```bash
java -version
javac -version
```

---

## Part 2: Installing an IDE

### Recommended: IntelliJ IDEA Community Edition
1. Download from [JetBrains website](https://www.jetbrains.com/idea/download/)
2. Install and launch
3. Create a new Java project

### Alternative: Visual Studio Code
1. Install VS Code
2. Install "Extension Pack for Java" extension

---

## Part 3: Your First Java Program

### Create HelloWorld.java

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### Understanding the Code:

1. **`public class HelloWorld`**
   - `public`: Access modifier (visible to all)
   - `class`: Keyword to create a class
   - `HelloWorld`: Name of the class (must match filename)

2. **`public static void main(String[] args)`**
   - Entry point of every Java program
   - `public`: Can be called from anywhere
   - `static`: Can be run without creating an object
   - `void`: Doesn't return any value
   - `main`: Method name (convention)
   - `String[] args`: Command line arguments

3. **`System.out.println("Hello, World!")`**
   - Prints text to console
   - `System`: Built-in class
   - `out`: Output stream
   - `println`: Print line method

---

## Part 4: Compiling and Running

### Using Command Line:

```bash
# Compile
javac HelloWorld.java

# Run
java HelloWorld
```

### Using IDE:
- Click the green "Run" button
- Or use keyboard shortcut (Shift+F10 in IntelliJ)

---

## Exercises

### Exercise 1: Personal Greeting
Create a program that prints your name and age:
```java
public class AboutMe {
    public static void main(String[] args) {
        // Your code here
        // Print your name
        // Print your age
        // Print your favorite hobby
    }
}
```

### Exercise 2: Multiple Lines
Print a simple pattern:
```
*****
*   *
*   *
*****
```

### Exercise 3: Add Comments
Modify your HelloWorld program to include:
- Single-line comments (`//`)
- Multi-line comments (`/* */`)
- Documentation comments (`/** */`)

---

## Common Errors and Solutions

### Error 1: "javac is not recognized"
**Solution**: JAVA_HOME not set correctly. Check environment variables.

### Error 2: "class name doesn't match filename"
**Solution**: Filename must be exactly the same as the public class name.

### Error 3: "Could not find or load main class"
**Solution**: Make sure you're in the correct directory and the .class file exists.

---

## Key Takeaways

- Java programs must have a `.java` extension
- Public class name must match the filename
- `main` method is the entry point
- Java is case-sensitive
- Every statement ends with a semicolon (`;`)
- Code blocks are enclosed in curly braces `{}`

---

## Next Steps

Move to Tutorial 2: Variables and Data Types once you can successfully compile and run Java programs.
