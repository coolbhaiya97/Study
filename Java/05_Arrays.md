# 05 – Arrays

## What is an Array?
- An array stores **multiple values of the same type** in a single variable.
- Fixed size – once created, the size cannot change.
- Index starts at **0**.

## Declaration & Initialization
```java
// Declaration only
int[] numbers;

// Declaration + allocation
int[] scores = new int[5];   // 5 elements, all initialized to 0

// Declaration + initialization with values
int[] primes = {2, 3, 5, 7, 11};
String[] fruits = {"Apple", "Banana", "Cherry"};
```

## Accessing Elements
```java
int[] arr = {10, 20, 30, 40, 50};

System.out.println(arr[0]);   // 10  (first element)
System.out.println(arr[4]);   // 50  (last element)
arr[2] = 99;                  // modify element
System.out.println(arr.length); // 5 (total number of elements)
```

## Iterating Over an Array
```java
int[] nums = {5, 10, 15, 20};

// Using a regular for loop
for (int i = 0; i < nums.length; i++) {
    System.out.println(nums[i]);
}

// Using enhanced for loop (for-each)
for (int n : nums) {
    System.out.println(n);
}
```

## Common Array Operations

### Finding the Maximum Value
```java
int[] arr = {3, 7, 1, 9, 4};
int max = arr[0];
for (int x : arr) {
    if (x > max) max = x;
}
System.out.println("Max = " + max);   // 9
```

### Sorting an Array
```java
import java.util.Arrays;

int[] arr = {5, 2, 8, 1};
Arrays.sort(arr);
System.out.println(Arrays.toString(arr));  // [1, 2, 5, 8]
```

## 2D Arrays (Matrix)
```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Access element at row 1, column 2
System.out.println(matrix[1][2]);  // 6

// Print all elements
for (int i = 0; i < matrix.length; i++) {
    for (int j = 0; j < matrix[i].length; j++) {
        System.out.print(matrix[i][j] + " ");
    }
    System.out.println();
}
```

## Arrays Class Utility Methods
```java
import java.util.Arrays;

int[] a = {3, 1, 4, 1, 5};
Arrays.sort(a);                      // sort in place
int idx = Arrays.binarySearch(a, 4); // find index of 4 (after sorting)
int[] copy = Arrays.copyOf(a, 3);    // [1, 1, 3]
boolean eq = Arrays.equals(a, copy); // false
System.out.println(Arrays.toString(a)); // [1, 1, 3, 4, 5]
```
