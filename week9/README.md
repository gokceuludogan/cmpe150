# Cmpe150 Week 9

#### Question 1

Write a function named **divide_with_remainder** which takes two integer values: number and divisor, and  two integer pointers (addresses of two integers): result and remainder. This function should divide the number by divisor, then write the result into the address given by result, and write the remainder into the address given by remainder.

```input
input: 8 3
output: 2 2
input: 11 5
output: 2 1
```

#### Question 2

Write a function takes two integer addresses as parameters and swaps the values addressed by these pointers. 

swap(int *num1, int *num2)

### Function Properties

- The callee should be defined before the caller
- Function prototypes:  signature of the function
  - function name, parameter type list, and return type.
  - long comb(int, int);
  - Now actual definition can come after main().
  - Generally put into *a header file*.
  - include the header file when using the library.

### Preprocessor Macros

#### Symbolic Constants: #define PI 3.14

#### Macros: #define ADD(x,y) ((x)+(y))

* Macros perform substitution.
* Parentheses are important.
* Not a function.

### C Libraries

* Input/Output, Math, String etc.
* Math Library:
  * #include <math.h>
  * Take double, return double
  * root, sine, power, log, etc.
* Standard Library:
  * Converting text to numeric
  * Memory allocation
  * Interaction with OS

## Arrays

* Hold multiple values of the **same type** (i.e. int, char, float, etc.)

* Each value is called **element**.

* Each element is accessed using **index**.

  ![img](https://github.com/hkmztrk/CMPE150/raw/5a68414c5a77b913cd253a240b734e594b25e8f3/week09/W09_01.PNG)

  ![img](https://github.com/hkmztrk/CMPE150/raw/5a68414c5a77b913cd253a240b734e594b25e8f3/week09/W09_02.PNG)

  ![img](https://github.com/hkmztrk/CMPE150/raw/5a68414c5a77b913cd253a240b734e594b25e8f3/week09/W09_03.PNG)

  * Trying to access an element beyond the bounds of an array can cause errors. Like numbers[100] in the example.

  * It can be initialized with 

    * loops 

      * ```c
        int i, array[5]; // n has 5 elements, n[0] to n[4]
        for(i=0; i<5; i++)
        	//array[i] = 0;
            scanf("%d", &array[i])
        ```

    * at declaration line

      * `int array[5] = {1, -4, 3, 9, -2};`
      * `int array[10] = {0};` // sets all to zero (since not given set to 0)
      * `int array[] = {1, -4, 3, 9, -2};` // also valid.

  * Variable array size: *int array[size_of_arr];*

  * Passing arrays to functions

    * *int max_of_array( int a[] )*

    * ```c
      int arr[10];
      ...
      max_of_array(arr)
      ```

    * Any change of the array elements is reflected to the caller.

  * The const modifier: Indicates that a parameter is **not supposed to be changed**. Compile Error!

  * Equality or copying must be performed elementwise!

#### Question 3

Write a program that reads 8 elements from the user and store them in an array. Then print elements which is larger than the average of numbers held in the array. 

```
input: 29 54 10 62 56 13 75	11 
output: 54 62 56 75
```

#### Question 4 (for Section 3) / Homework (for Section 2)

Write a program which reads an integer N from the user, then reads N integers from the user into an array. Then copy this array to another array but in reverse order.

```
input: 
6
3 0 1 63 26 72
arr1 = {3, 0, 1, 63, 26, 72}
arr2 = {72, 26, 63, 1, 0, 3}
```