# Cmpe150.03 Week 5

### Warm up

Write a program to input two numbers from user and find maximum between two numbers using if else and switch case.

```
input: 40 30
output: 40
```

## Loops

**While, do/while, for**

### while loops

* controlled by a boolean expression like if

* determines how many times statement in code block will execute

* Repeat until the expression becomes **false**.

  ```
  while (<boolean_expression>)
  	<statement>
  ```

  <img src="figures/1571759785622.png" alt="1571759785622" style="zoom:50%;" />

  

  * Loop control variable *i*
  
    ```c
    int i = 0; // initialize
    while (i < n) { // test
    	printf("*"); 
    	i++; //update
    }
    ```
  

How can we end up in an infinite loop?

#### Question 1

  ##### a.

  Write a program that takes an integer as input and computes the sum of positive integers up to that integer using while loops. 

```
input: 3
output: 6

input: 5
output: 15
```

  ##### b.

  Write a program that takes an integer as input and computes the sum of positive odd integers up to that integer using while loops. 

```
input: 3
output: 4

input: 5
output: 9
```

  #### Question 2

  Write a program which reads an integer (smaller than 1000000) then prints out how many of the digits are odd numbers.

``` 
input: 16283 
output: 2

input: 15672
output 3
```

  ## do-while loops

  First statement is executed, then expression is evaluated. 

```c
do
	<statement>
while (<boolean_expression>);
```

<img src="figures/1571760221894.png" alt="1571760221894" style="zoom:50%;" />



  

  #### Question 3

Write a program that take integers as inputs until the user enters negative number and show the maximum number entered by user.

````
input: 8 3 0 105 18
output: 105
  
input: 75 7 1 5 39 45 67
output: 75
````

## for loops

for statement includes the three parts needed for loops: initialize, test, and update. 

```c
for (<initialize>; <boolean_expression>; <update>){
	<statement>
}
```

<img src="C:/Cmpe150-Fall19/lab-materials/fall19/week6/figures/1571761472620.png" alt="1571761472620" style="zoom:50%;" />





## continue and break

![Working of break statement](https://cdn.programiz.com/sites/tutorial2program/files/c-break-statement-works.jpg)

![Working of continue statement in C programming](https://cdn.programiz.com/sites/tutorial2program/files/c-continue-statement-works.jpg)



#### Question 4

Write a program that takes two characters from user and displays characters between these.

```
input: a e
output: a b c d e
```

#### Question 5

Write a program which reads a positive integer number N , and prints the Nth fibonacci number. *0, 1, 1, 2, 3, 5, ...*  

F_0 = 0, F_1 = 1, F_n = F_(n-2) + F_(n-1)

```
input: 4
output: 2
input: 6
output: 5
```

#### Question 6

##### a.

Write a program which takes an integer as input and prints whether the number is prime or not.

```
input: 7
output: prime

input: 8
output: not prime
```

##### b.

Write a program which takes an integer as input and prints prime numbers up to that integer.

```
input: 11
output: 2 3 5 7 

input: 15
output: 2 3 5 7 11 13
```

  ## References

https://www.cs.cmu.edu/~mrmiller/15-110/

https://www.programiz.com/c-programming/c-break-continue-statement