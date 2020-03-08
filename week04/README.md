# Cmpe150.04 Week 4

### Operators*

- Assignment Operators (=, +=, -=, *=, /=)
- Arithmetic Operators (+, -, *, /, %)
- Increment-Decrement (++, --)
- Logical Operators (&&, ||, !)
  - Zero => False
  - Nonzero => True
- Relational Operators (>, <, >=, <=, ==, !=)
- Precedence: Parentheses > Arithmetic Operators > Comparison Operators > Logical Operators > Assignment Operators

## Char

* Represent characters.

* Maps characters to integers using ASCII table.

* ASCII Table: Letters and digits are consecutive.

  | Syntax | Meaning       |
  | ------ | ------------- |
  | a      | variable name |
  | 'a'    | character     |
  | "a"    | string        |

## Warm up

Write a program that reads two digit as char and print multiplication of them. 

```
input: 7 8
output: 56
```

## Conditional Statements

* alters the flow of control
* **if, if-else, and switch**

### If statements

```c 
if (boolean_expression)
{
    statements
}
```

![1583474232710](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1583474232710.png)



### if else statement

```c
if (boolean_expression)
	statement1
else
	statement2
```

![1583474306401](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1583474306401.png)

### else if

* useful when checking multiple conditions.

```c
if (boolean_expression)
	statement1
else if (boolean_expression)
	statement2
else
	statement3
```

* **else** is optional. 

### nested if

```c
if(boolean_expression) {
    //Nested if else inside the body of "if"
    if(boolean_expression) {
       //Statements inside the body of nested "if"
    }
    else {
       //Statements inside the body of nested "else"
    }
}
else {
    //Statements inside the body of "else"
}
```

### ternary if else: condition ? value1 : value2

* Example: Get the larger of two variables ```a = (b>c) ? b : c;```

### Question 1

Write a program that takes year as input and prints whether a given year is a leap year or not.

```
input: 2018
output: not a leap year

input: 2020
output: a leap year
```

### Question 2

Write a program to accept a coordinate point in a XY coordinate system and determine in which quadrant the coordinate point lies. 

```
input: 5 7
output: The point (5, 7) lies in the first quadrant. 

input: -2 -5
output: The point (-2, -5) lies in the third quadrant.
```

### Question 3

Write a program that takes two integers and an operation as char (*, /, +, -) and performs the operations and prints. 

```
input: 3 5 *
output: 15
input: 10 7 +
output: 17
```

### Question 4

Write a program that takes three integers and find the largest one. 

```
input: 4 1 -3
output: 4

input: 5 19 2
output: 19
```

### Switch case

- When a matching case is found, the program will execute all the cases below it as well.

- Use the break command to end the switch statement and skip remaining cases.

  ```c
  char command = 'b';
  switch(command)
  {
      case 'a':
      case 'A': printf("Plan A\n");
      break;
      case 'b':
      case 'B': printf("Plan B\n");
      break;
      default : printf("I have no plans.\n"); // optional
  }
  ```

  

##### What if we forget *break*?

### Question 5

Write a program that takes a number in range (1, 7) and prints corresponding day of week using switch case

```
input: 3
output: wednesday
```

### Question 6

Write a program to input two numbers from user and find maximum between two numbers using switch case.

```
input: 40 30
output: 40
```

### References

https://codeforwin.org/2015/05/if-else-programming-practice.html

https://beginnersbook.com/2014/01/c-if-else-statement-example/

***** [https://github.com/suyunu/c-notes/tree/master/Week_04](https://github.com/suyunu/c-notes/tree/master/Week_04)





![img](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191202113149/CPP-Decision-Making.png)

