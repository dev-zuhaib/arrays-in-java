# Arrays in Java - Comprehensive Revision Guide By Zuhaib Sir

### Table of Contents
1. [Introduction to Arrays](#introduction-to-arrays)
2. [Single Dimensional Arrays](#single-dimensional-arrays)
    - [Definition and Declaration](#definition-and-declaration)
    - [Initialization](#initialization)
    - [Accessing Elements](#accessing-elements)
    - [Common Operations](#common-operations)
        - [Finding Minimum/Maximum](#finding-minimummaximum)
        - [Reversing an Array](#reversing-an-array)
        - [Linear Search](#linear-search)
        - [Binary Search](#binary-search)
        - [Selection Sort](#selection-sort)
        - [Bubble Sort](#bubble-sort)
3. [Double Dimensional Arrays](#double-dimensional-arrays)
    - [Definition and Declaration](#definition-and-declaration-1)
    - [Initialization](#initialization-1)
    - [Accessing Elements](#accessing-elements-1)
    - [Common Operations](#common-operations-1)
        - [Transpose of a Matrix](#transpose-of-a-matrix)
        - [Equality of Two Matrices](#equality-of-two-matrices)
        - [Sum of Rows](#sum-of-rows)
        - [Sum of Columns](#sum-of-columns)
        - [Sum of Diagonals](#sum-of-diagonals)
        - [Matrix Display](#matrix-display)
4. [Conclusion](#conclusion)

---

## Introduction to Arrays

An array is a collection of elements of the same type placed in contiguous memory locations. Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value.

---

## Single Dimensional Arrays

### Definition and Declaration

A single dimensional array is a list of elements, all of the same type, accessed by a single index.

```java
// Declaration
int[] array;
```

### Initialization

You can initialize an array at the time of declaration or later in the code.

```java
// Initialization at the time of declaration
int[] array = {1, 2, 3, 4, 5};

// Initialization after declaration
array = new int[5];
array[0] = 1;
array[1] = 2;
array[2] = 3;
array[3] = 4;
array[4] = 5;
```

### Accessing Elements

Elements in an array are accessed using their index.

```java
int firstElement = array[0]; // Accessing the first element
int secondElement = array[1]; // Accessing the second element
```

### Common Operations

#### Finding Minimum/Maximum

```java
public class MinMax {
    public static void main(String[] args) {
        int[] array = {5, 2, 8, 3, 9};
        int min = array[0];
        int max = array[0];
        
        for (int i = 1; i < array.length; i++) {
            if (array[i] < min) {
                min = array[i];
            }
            if (array[i] > max) {
                max = array[i];
            }
        }
        
        System.out.println("Minimum: " + min);
        System.out.println("Maximum: " + max);
    }
}
```

#### Reversing an Array

```java
public class ReverseArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int n = array.length;
        
        for (int i = 0; i < n / 2; i++) {
            int temp = array[i];
            array[i] = array[n - 1 - i];
            array[n - 1 - i] = temp;
        }
        
        for (int i : array) {
            System.out.print(i + " ");
        }
    }
}
```

#### Linear Search

```java
public class LinearSearch {
    public static void main(String[] args) {
        int[] array = {4, 2, 7, 1, 9};
        int key = 7;
        boolean found = false;
        
        for (int i = 0; i < array.length; i++) {
            if (array[i] == key) {
                found = true;
                System.out.println("Element found at index: " + i);
                break;
            }
        }
        
        if (!found) {
            System.out.println("Element not found.");
        }
    }
}
```

#### Binary Search

```java
import java.util.Arrays;

public class BinarySearch {
    public static void main(String[] args) {
        int[] array = {3, 6, 8, 12, 14};
        int key = 8;
        Arrays.sort(array);
        int result = Arrays.binarySearch(array, key);
        
        if (result >= 0) {
            System.out.println("Element found at index: " + result);
        } else {
            System.out.println("Element not found.");
        }
    }
}
```

#### Selection Sort

```java
public class SelectionSort {
    public static void main(String[] args) {
        int[] array = {64, 25, 12, 22, 11};
        
        for (int i = 0; i < array.length - 1; i++) {
            int minIdx = i;
            for (int j = i + 1; j < array.length; j++) {
                if (array[j] < array[minIdx]) {
                    minIdx = j;
                }
            }
            
            int temp = array[minIdx];
            array[minIdx] = array[i];
            array[i] = temp;
        }
        
        for (int i : array) {
            System.out.print(i + " ");
        }
    }
}
```

#### Bubble Sort

```java
public class BubbleSort {
    public static void main(String[] args) {
        int[] array = {5, 1, 4, 2, 8};
        
        for (int i = 0; i < array.length - 1; i++) {
            for (int j = 0; j < array.length - 1 - i; j++) {
                if (array[j] > array[j + 1]) {
                    int temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                }
            }
        }
        
        for (int i : array) {
            System.out.print(i + " ");
        }
    }
}
```

---

## Double Dimensional Arrays

### Definition and Declaration

A double dimensional array is an array of arrays. It can be used to represent a matrix.

```java
// Declaration
int[][] matrix;
```

### Initialization

You can initialize a double dimensional array at the time of declaration or later in the code.

```java
// Initialization at the time of declaration
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Initialization after declaration
matrix = new int[3][3];
matrix[0][0] = 1;
matrix[0][1] = 2;
matrix[0][2] = 3;
matrix[1][0] = 4;
matrix[1][1] = 5;
matrix[1][2] = 6;
matrix[2][0] = 7;
matrix[2][1] = 8;
matrix[2][2] = 9;
```

### Accessing Elements

Elements in a double dimensional array are accessed using two indices.

```java
int element = matrix[1][2]; // Accessing the element at row 1, column 2
```

### Common Operations

#### Transpose of a Matrix

```java
public class TransposeMatrix {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        
        int[][] transpose = new int[matrix[0].length][matrix.length];
        
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                transpose[j][i] = matrix[i][j];
            }
        }
        
        for (int i = 0; i < transpose.length; i++) {
            for (int j = 0; j < transpose[0].length; j++) {
                System.out.print(transpose[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

#### Equality of Two Matrices

```java
public class MatrixEquality {
    public static void main(String[] args) {
        int[][] matrix1 = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int[][] matrix2 = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        
        boolean equal = true;
        
        if (matrix1.length != matrix2.length || matrix1[0].length != matrix2[0].length) {
            equal = false;
        } else {
            for (int i = 0; i < matrix1.length; i++) {
                for (int j = 0; j < matrix1[0].length; j++) {
                    if (matrix1[i][j] != matrix2[i][j]) {
                        equal = false;
                        break;
                    }
                }
            }
        }
        
        if (equal) {
            System.out.println("The matrices are equal.");
        } else {
            System.out.println("The matrices are not equal.");
        }
    }
}
```

#### Sum of Rows

```java
public class SumOfRows {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        
        for (int i = 0; i < matrix.length; i++) {
            int sum = 0;
            for (int j = 0; j < matrix[0].length; j++) {
                sum += matrix[i][j];
            }
            System.out.println("Sum of row " + i + ": " + sum);
        }
    }
}
```

#### Sum of Columns

```java
public class SumOfColumns {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        
        for (int i = 0; i < matrix[0].length; i++) {
            int sum = 0;
            for (int j = 0; j < matrix.length; j++) {
                sum += matrix[j][i];
            }
            System.out.println("Sum of column " + i + ": " + sum);
        }
    }
}
```

#### Sum of Diagonals

```java
public class SumOfDiagonals {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        
        int leftDiagonalSum = 0;
        int rightDiagonalSum = 0;
        
        for (int i = 0; i < matrix.length; i++) {
            leftDiagonalSum += matrix[i][i];
            rightDiagonalSum += matrix[i][matrix.length - 1 - i];
        }
        
        System.out.println("Sum of left diagonal: " + leftDiagonalSum);
        System.out.println("Sum of right diagonal: " + rightDiagonalSum);
    }
}
```

#### Matrix Display

```java
public class MatrixDisplay {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

---

## Conclusion

This guide covers the basics to advanced topics of arrays in Java, including both single and double-dimensional arrays. Practice the examples and understand the concepts thoroughly to excel in your exam. Good luck!
