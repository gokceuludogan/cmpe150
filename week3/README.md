# Cmpe150.03 Week3

## Mail: cmpe150.mail@gmail.com

## Errors

### Compile Time Errors

* Violating rules of writing syntax of C code. 

  * Missing parenthesis
  * Missing semicolon
  * Printing value without declaration

* Examples

  * ![1570300391805](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570300391805.png)

    ![1570300492161](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570300492161.png)

  * ![1570300588514](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570300588514.png)

    ![1570300636310](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570300636310.png)

    

### Run Time Errors

* Errors cannot be detected by compilers and occur during program execution. 
* Example:
  * Division by zero. 
  * Logic errors.

## Warnings 

* ![1570300699622](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570300699622.png)

  

  ![1570300750532](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570300750532.png)

* ![1570300948268](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570300948268.png)

  ![1570300973481](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570300973481.png)

* ![1570302473710](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570302473710.png)

  

  ![1570302539152](C:\Users\gokce\AppData\Roaming\Typora\typora-user-images\1570302539152.png)

### Warm up

Write a program that takes an integer from user and does following operations in an expression and prints result with only two decimal points.:

* Divide by 3
* Add 10
* Multiply with 2

```
input: 15
output: 30.00

input: 7
output: 24.66
```



## Operators

### Assignment Operators (=, )

* <variable> = <expression>
* Assign the value of the expression to the variable
* Right to left associative:  
  * ```a = b = c = 10;```  ``` a = (b = (c = 10));```
* Initialization:
  * int a = 3, b = 4;
    float x = 2.75;
* Compound assignment operator: 
  * a = a + b;
    a += b;

#### Type Conversion

* Narrow to broader (i.e. int to float, 3 => 3.0): no loss of information. 

* Broad to narrower (i.e. float to int, 3.5 => 3): lost info. 

  

### Arithmetic Operators (+, -, *, /, %)

* The results of an operator expression is of the "wider" type (int < float < double)

* Integer division vs Float division

* Float division of integers: Multiply with 1.0 or cast into float. 

* Left to right associative: ```a/b/c```  <=>```(a/b)/c```

* Variable updates: 

  * x = x +1, 

  * ++, --: pre/post 

    

### Logical Operators

* Boolean operations (true vs false) 
  * Zero => false
  * Nonzero => true
* Operators: 
  * "&&" logical-AND
  *  "||" logical-OR 
  *  "!" negation



### Relational Operators

* Value comparisons: 1 if true else 0

| **Operators** | **Example/Description**                  |
| ------------- | ---------------------------------------- |
| >             | x > y (x is greater than y)              |
| <             | x < y (x is less than y)                 |
| >=            | x >= y (x is greater than or equal to y) |
| <=            | x <= y (x is less than or equal to y)    |
| ==            | x == y (x is equal to y)                 |
| !=            | x != y (x is not equal to y)             |

### Expressions and precedence

- Highest precedence: Parentheses
- *, /, % are evaluated before +, -
- **Arithmetic Operators > Comparison Operators > Logical Operators > Assignment Operators**
- Associativity is used when there are two or more operators of same precedence

## Data Type: Char

- Represent characters (letters, digits, signs)

- 1 byte = 8 bits = 256 values.

- **Encoding:** Mapping characters to strings (integer values mostly)

  - ASCII table: maps 256 characters.

    ![](https://cdn.shopify.com/s/files/1/1014/5789/files/Standard-ASCII-Table_large.jpg?10669400161723642407)

    ![](https://cdn.shopify.com/s/files/1/1014/5789/files/Extended-ASCII-Table_large.jpg?14948660931384897703)

  - Letters and digits are consecutive. 

  - Variable stores corresponding integer value of character. The translation is done by i/o functions.

  | Syntax | Meaning       |
  | ------ | ------------- |
  | a      | variable name |
  | 'a'    | character     |
  | "a"    | string        |

  - Create chars, print characters and corresponding integer values. (%c, %d)

### Question1

Write a program takes a lowercase letter as input and converts it to uppercase and prints.

```
input: h
output: H
```

## Symbolic Constants

- #define 
- Cannot be changed, fixed value.
- Changes all occurrences of that name with given value. 
- Syntax: #define constant_name constant_value

### Question2

Write a program to convert height from centimetres to feet.

```
define constants: 
INCHES_IN_FOOT = 12 // 1 foot = 12 inches 
CM_IN_INCH=2.54 // 1 inch = 2.54 cms 
height in cm, read from user

input: 180
output: 5.9055
```

### Question3 

Write a program that reads an integer and prints 1 if it is odd and prints 0 if it is even.

```
input: 3 
output: 1

input: 18
output: 0
```

### Question4

Write a program that reads one character as input and print 1 if it is a digit else 0. 

```
input: 7
output: 1

input: a
output: 0
```

### Question5

Write a program that takes three integer from user and calculates the sum of the odd ones. 

```
input: 1 3 5
output: 9

input: 2 7 1
output: 8
```



## References

* https://www.geeksforgeeks.org/errors-in-cc/

* https://www.commfront.com/pages/ascii-chart

* https://fresh2refresh.com/c-programming/c-operators-expressions/c-relational-operators/

  