# Week 7 - Functions

<details><summary><bold>Function Syntax</bold></summary><img src='https://www.geeksforgeeks.org/wp-content/uploads/Function-Prototype-in-c.png'/></details>

#### Question 1

Write a function **to_upper()** which takes **a char** as input, and returns the upper case version of the character if it is a lower case letter. Otherwise it should return the same character.

Then write a program which reads a word from the user, and prints it with upper case characters. Assume valid words will be given.

| Input    | Output   |
| -------- | -------- |
| cMpe     | CMPE     |
| funCTi0n | FUNCTI0N |

#### Question 2

Write a function **find_max()** which takes three integers as parameters and returns **maximum** among them. Then, call this function in main() function with the following inputs and print corresponding outputs.

| Input   | Output |
| ------- | ------ |
| 5 3 8   | 8      |
| 14 -1 9 | 14     |

#### Question 3

Write functions that compute the factorial f(n)=n!, permutation, P(n,k)=n!/(n-k)!, and the combinatorial, C(n,k)=n!/(n-k)! k!, of two numbers n and k, where n>0, k>0, and n ≥ k. 

Then write a function named **selection** whose parameters are a char and two integers. If the character is **C**, calls combinatorial function with the integer parameters and return the result. If the character is **P**, calls permutation function and return the result. Otherwise, returns -1.

| Function    | Input | Output |
| ----------- | ----- | ------ |
| factorial   | 5     | 120    |
| permutation | 5 2   | 20     |
| combination | 5 2   | 10     |
| selection   | C 5 2 | 10     |
| selection   | P 5 2 | 20     |
| selection   | X 5 2 | -1     |

#### Question 4

Write a function named **fetchDigit** which takes two integers as input: **number** and **n**. Function should return the nth digit (from the right) of the number as an integer. If the number is less than n digits, Function should return -1. 

Then write a program which reads a positive integer z and another integer x, then print out the xth digit of z. If the input is incorrect (z doesn't have x digits), program should print "Incorrect input". Assume negative integers will not be given. 

| Input    | Output          |
| -------- | --------------- |
| 23423 3  | 4               |
| 204602 5 | 0               |
| 52 9     | Incorrect input |

#### Question 5

Write a function named **pyramid** which takes an integer as input: **num_of_rows**, then prints the pyramid of numbers increased by 1 shown below. This function shouldn't return anything.

| Input | Output                                    |
| ----- | ----------------------------------------- |
| 4     | &nbsp;&nbsp;&nbsp;1<br />&nbsp;&nbsp;2 3<br />&nbsp;4 5 6<br />7 8 9 10 |
| 3     | &nbsp;&nbsp;1<br />&nbsp;2 3<br />4 5 6                   |

#### Question 6

Write a function **is_perfect()** that checks whether the given number is perfect. Perfect number is a positive integer that is equal to the sum of its positive divisors excluding the number itself. The function prints the positive divisors and returns 1 if the number is perfect and returns 0 otherwise. 

| Input | Output     | Return |
| ----- | ---------- | ------ |
| 5     | 1 5        | 0      |
| 6     | 1 2 3      | 1      |
| 28    | 1 2 4 7 14 | 1      |
| 12    | 1 2 3 4 6  | 0      |

#### Question 7

Write a function that will take an integer number and return its reverse version as another integer. Then fill/write main() appropriately to see the result.		

| Input | Output |
| ----- | ------ |
| 1234  | 4321   |
| 68436 | 63486  |

#### Question 8

Write a function that will take an integer as a parameter. Then calculates and returns its binary version as another integer. Then write main appropriately to see the result.	

| Input | Output     |
| ----- | ---------- |
| 25    | 11001      |
| 532   | 1000010100 |
| 5     | 101        |

#### Question 9

Write a function that will take a positive integer n, and returns the nth Fibonacci number. Then write main appropriately to see the result.

| Input | Output |
| ----- | ------ |
| 1     | 0      |
| 2     | 1      |
| 3     | 1      |
| 4     | 2      |
| 5     | 3      |
| 10    | 34     |
| 15    | 377    |
