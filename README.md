# Arrays in Java

An array is a collection of objects of similar type, stored in contiguous memory locations. Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value.

## Types of Arrays
1. Single Dimensional Array (Linear Array)
2. Double Dimensional Array (2D Array)

### Single Dimensional Array
A single dimensional array is a list of elements stored in a single row. It is also referred to as a linear array.

#### Example
```java
int[] arr = {2, 3, 5, 7, 10};
```

#### Syntax for Defining a Single Dimensional Array
```java
<Data type> <Array_name> [] = new <Data type> [size];
```

#### Notes
1. Arrays are always of fixed size, meaning once defined, an array's size cannot be increased or decreased.
2. In arrays, the position of any element is called an index.
3. The index starts from `0` and goes up to the end of the array.
4. Therefore, the index of the first element is `0`.
5. The index of the last element of the array is `length - 1`.

#### Getting the Length of an Array
The `arr.length` property returns the length/size of the array.
```java
int length = arr.length;
```

#### Storing an Element at Any Index of an Array
You can store an element at a specific index of an array using the following syntax:
```java
arr[index] = value;
```
Example:
```java
arr[0] = 10; // The first element of the array will be 10.
```

#### Getting an Element from an Array at a Specific Index
You can retrieve an element from a specific index of an array using the following syntax:
```java
System.out.println(arr[0]); // Prints the first element of the array.
```

### Looping Through an Array
You can loop through an array using different types of loops such as `for`, `while`, and `for-each` loops.

#### Using a For Loop
```java
int[] arr = {2, 3, 5, 7, 10};
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

#### Using a While Loop
```java
int[] arr = {2, 3, 5, 7, 10};
int i = 0;
while (i < arr.length) {
    System.out.println(arr[i]);
    i++;
}
```

#### Using a For-Each Loop
```java
int[] arr = {2, 3, 5, 7, 10};
for (int num : arr) {
    System.out.println(num);
}
```

### Example: Print Sum of Elements of an Array
```java
int[] arr = {2, 3, 5, 7, 10};
int sum = 0;
for (int num : arr) {
    sum += num;
}
System.out.println("Sum of elements: " + sum);
```

### Double Dimensional Array
A double dimensional array is a list of elements stored in a matrix format (rows and columns). It is also referred to as a 2D array.

#### Example
```java
int[][] arr = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

#### Syntax for Defining a Double Dimensional Array
```java
<Data type> <Array_name> [][] = new <Data type> [rows][columns];
```

#### Notes
1. Similar to single dimensional arrays, double dimensional arrays are also of fixed size.
2. The elements in a 2D array are accessed using row and column indices.

#### Getting the Length of a 2D Array
The `arr.length` property returns the number of rows in the array.
```java
int rows = arr.length;
```
To get the number of columns in a specific row:
```java
int columns = arr[0].length;
```

#### Storing an Element at Any Index of a 2D Array
You can store an element at a specific row and column index of a 2D array using the following syntax:
```java
arr[rowIndex][columnIndex] = value;
```
Example:
```java
arr[0][0] = 1; // The first element of the first row will be 1.
```

#### Getting an Element from a 2D Array at a Specific Index
You can retrieve an element from a specific row and column index of a 2D array using the following syntax:
```java
System.out.println(arr[0][0]); // Prints the first element of the first row.
```

### Looping Through a 2D Array
You can loop through a 2D array using nested loops.

#### Using Nested For Loops
```java
int[][] arr = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
for (int i = 0; i < arr.length; i++) {
    for (int j = 0; j < arr[i].length; j++) {
        System.out.println(arr[i][j]);
    }
}
```

### Example: Print Sum of Elements of a 2D Array
```java
int[][] arr = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
int sum = 0;
for (int i = 0; i < arr.length; i++) {
    for (int j = 0; j < arr[i].length; j++) {
        sum += arr[i][j];
    }
}
System.out.println("Sum of elements: " + sum);
```
