# Tutorial 7: Arrays in Java

Arrays store multiple values of the same type in a single variable.

---

## What is an Array?

An array is a container that holds a fixed number of values of a single type.

### Key Points:
- Fixed size (cannot be changed after creation)
- Same data type for all elements
- Zero-indexed (first element at index 0)

---

## 1. Single-Dimensional Arrays

### Declaration:
```java
dataType[] arrayName;
// or
dataType arrayName[];
```

### Initialization:

#### Method 1: Declare then allocate
```java
int[] numbers;
numbers = new int[5];  // Array of 5 integers
```

#### Method 2: Declare and allocate together
```java
int[] numbers = new int[5];
```

#### Method 3: Declare, allocate, and initialize
```java
int[] numbers = {10, 20, 30, 40, 50};
```

### Example:
```java
public class ArrayDemo {
    public static void main(String[] args) {
        // Create array
        int[] numbers = new int[5];

        // Assign values
        numbers[0] = 10;
        numbers[1] = 20;
        numbers[2] = 30;
        numbers[3] = 40;
        numbers[4] = 50;

        // Access elements
        System.out.println(numbers[0]);  // 10
        System.out.println(numbers[2]);  // 30

        // Array length
        System.out.println("Length: " + numbers.length);  // 5
    }
}
```

---

## 2. Initializing Arrays

### Direct Initialization:
```java
int[] numbers = {1, 2, 3, 4, 5};
String[] fruits = {"Apple", "Banana", "Orange"};
double[] prices = {19.99, 29.99, 39.99};
boolean[] flags = {true, false, true};
```

### Default Values:
```java
int[] numbers = new int[3];     // {0, 0, 0}
String[] names = new String[3];  // {null, null, null}
boolean[] flags = new boolean[3]; // {false, false, false}
double[] values = new double[3];  // {0.0, 0.0, 0.0}
```

---

## 3. Accessing Array Elements

```java
public class ArrayAccess {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};

        // Access by index
        System.out.println("First: " + numbers[0]);    // 10
        System.out.println("Last: " + numbers[4]);     // 50

        // Modify element
        numbers[2] = 100;
        System.out.println("Modified: " + numbers[2]);  // 100

        // Array length
        System.out.println("Length: " + numbers.length);

        // Last element using length
        System.out.println("Last: " + numbers[numbers.length - 1]);
    }
}
```

---

## 4. Iterating Through Arrays

### Using for Loop:
```java
int[] numbers = {10, 20, 30, 40, 50};

for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

### Using Enhanced for Loop (for-each):
```java
int[] numbers = {10, 20, 30, 40, 50};

for (int num : numbers) {
    System.out.println(num);
}
```

### Example: Sum of Array Elements
```java
public class ArraySum {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        int sum = 0;

        for (int num : numbers) {
            sum += num;
        }

        System.out.println("Sum: " + sum);  // 150
    }
}
```

---

## 5. Multi-Dimensional Arrays

### 2D Arrays (Matrix):

#### Declaration and Initialization:
```java
// Method 1
int[][] matrix = new int[3][3];  // 3x3 matrix

// Method 2
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

#### Accessing Elements:
```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

System.out.println(matrix[0][0]);  // 1
System.out.println(matrix[1][2]);  // 6
System.out.println(matrix[2][1]);  // 8
```

#### Iterating 2D Array:
```java
public class TwoDArrayDemo {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        // Using nested for loops
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }

        // Using enhanced for loop
        for (int[] row : matrix) {
            for (int num : row) {
                System.out.print(num + " ");
            }
            System.out.println();
        }
    }
}
```

### Jagged Arrays (Irregular):
```java
int[][] jagged = {
    {1, 2},
    {3, 4, 5},
    {6, 7, 8, 9}
};

for (int[] row : jagged) {
    for (int num : row) {
        System.out.print(num + " ");
    }
    System.out.println();
}
```

---

## 6. Common Array Operations

### Find Maximum:
```java
int[] numbers = {45, 23, 78, 12, 89, 34};
int max = numbers[0];

for (int num : numbers) {
    if (num > max) {
        max = num;
    }
}
System.out.println("Maximum: " + max);  // 89
```

### Find Minimum:
```java
int[] numbers = {45, 23, 78, 12, 89, 34};
int min = numbers[0];

for (int num : numbers) {
    if (num < min) {
        min = num;
    }
}
System.out.println("Minimum: " + min);  // 12
```

### Average:
```java
int[] numbers = {10, 20, 30, 40, 50};
int sum = 0;

for (int num : numbers) {
    sum += num;
}

double average = (double) sum / numbers.length;
System.out.println("Average: " + average);  // 30.0
```

### Search (Linear Search):
```java
int[] numbers = {10, 20, 30, 40, 50};
int target = 30;
int index = -1;

for (int i = 0; i < numbers.length; i++) {
    if (numbers[i] == target) {
        index = i;
        break;
    }
}

if (index != -1) {
    System.out.println("Found at index: " + index);
} else {
    System.out.println("Not found");
}
```

### Reverse Array:
```java
int[] numbers = {1, 2, 3, 4, 5};

for (int i = 0; i < numbers.length / 2; i++) {
    int temp = numbers[i];
    numbers[i] = numbers[numbers.length - 1 - i];
    numbers[numbers.length - 1 - i] = temp;
}

// Result: {5, 4, 3, 2, 1}
```

---

## 7. Arrays Class (Utility Methods)

Import: `import java.util.Arrays;`

### Sort Array:
```java
import java.util.Arrays;

int[] numbers = {45, 23, 78, 12, 89};
Arrays.sort(numbers);
System.out.println(Arrays.toString(numbers));
// [12, 23, 45, 78, 89]
```

### Binary Search:
```java
import java.util.Arrays;

int[] numbers = {12, 23, 45, 78, 89};  // Must be sorted
int index = Arrays.binarySearch(numbers, 45);
System.out.println("Index: " + index);  // 2
```

### Fill Array:
```java
import java.util.Arrays;

int[] numbers = new int[5];
Arrays.fill(numbers, 10);
System.out.println(Arrays.toString(numbers));
// [10, 10, 10, 10, 10]
```

### Copy Array:
```java
import java.util.Arrays;

int[] original = {1, 2, 3, 4, 5};
int[] copy = Arrays.copyOf(original, original.length);
System.out.println(Arrays.toString(copy));
// [1, 2, 3, 4, 5]
```

### Compare Arrays:
```java
import java.util.Arrays;

int[] arr1 = {1, 2, 3};
int[] arr2 = {1, 2, 3};
boolean equal = Arrays.equals(arr1, arr2);
System.out.println("Equal: " + equal);  // true
```

---

## Practical Examples

### Example 1: Student Marks System
```java
import java.util.Scanner;

public class StudentMarks {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("How many students? ");
        int n = scanner.nextInt();

        int[] marks = new int[n];

        // Input marks
        for (int i = 0; i < n; i++) {
            System.out.print("Enter marks for student " + (i + 1) + ": ");
            marks[i] = scanner.nextInt();
        }

        // Calculate statistics
        int sum = 0;
        int max = marks[0];
        int min = marks[0];

        for (int mark : marks) {
            sum += mark;
            if (mark > max) max = mark;
            if (mark < min) min = mark;
        }

        double average = (double) sum / n;

        System.out.println("\n--- Results ---");
        System.out.println("Total: " + sum);
        System.out.println("Average: " + average);
        System.out.println("Highest: " + max);
        System.out.println("Lowest: " + min);

        scanner.close();
    }
}
```

### Example 2: Matrix Addition
```java
public class MatrixAddition {
    public static void main(String[] args) {
        int[][] matrix1 = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        int[][] matrix2 = {
            {9, 8, 7},
            {6, 5, 4},
            {3, 2, 1}
        };

        int[][] result = new int[3][3];

        // Add matrices
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                result[i][j] = matrix1[i][j] + matrix2[i][j];
            }
        }

        // Display result
        System.out.println("Result:");
        for (int[] row : result) {
            for (int num : row) {
                System.out.print(num + " ");
            }
            System.out.println();
        }
    }
}
```

---

## Exercises

### Exercise 1: Second Largest
Find the second largest element in an array.

### Exercise 2: Remove Duplicates
Remove duplicate elements from an array.

### Exercise 3: Rotate Array
Rotate array elements to the right by k positions.
Example: [1,2,3,4,5] rotated by 2 becomes [4,5,1,2,3]

### Exercise 4: Merge Arrays
Merge two sorted arrays into one sorted array.

### Exercise 5: Matrix Transpose
Find transpose of a 3x3 matrix.

### Exercise 6: Frequency Counter
Count frequency of each element in an array.

---

## Common Errors

1. **ArrayIndexOutOfBoundsException**
   ```java
   int[] arr = {1, 2, 3};
   System.out.println(arr[3]);  // ERROR: index 3 doesn't exist
   ```

2. **NullPointerException**
   ```java
   int[] arr;
   System.out.println(arr[0]);  // ERROR: array not initialized
   ```

3. **Wrong length**
   ```java
   int[] arr = {1, 2, 3};
   System.out.println(arr.length());  // ERROR: length is property, not method
   System.out.println(arr.length);    // CORRECT
   ```

---

## Key Takeaways

- Arrays store multiple values of same type
- Fixed size, zero-indexed
- Access elements using index: `arr[0]`
- Get length using: `arr.length`
- Use `Arrays` class for utility methods
- 2D arrays for matrices
- Enhanced for loop for easy iteration

---

## Next Steps

Move to Tutorial 8: Strings to learn about String manipulation in Java.
