# Cmpe150.04 Week3

### Warm up

Write a program that takes an integer from user and does following operations in an expression and prints result with only two decimal points.:

* Divide by 3
* Add 10
* Multiply with 2

```c
input: 15
output: 30.00

input: 7
output: 24.67
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

* Explicitly: (type) expression

  * int y = 18;
  * float x = ((float) y + 3) / 5;
  
* ```c
  #include <stdio.h>
  #include <stdlib.h>
  
  int main() {
  	float x = 3.75;
  	printf("%f ", x); // Outputs 3.750000
  	int y = x;
  	printf("%d ", y); // Outputs 3
  	x = y;
  	printf("%f", x); // Outputs 3.000000
  	return 0;
  }
  
  ```

### Arithmetic Operators (+, -, *, /, %)

* The results of an operator expression is of the "wider" type (int < float < double)

* Integer division vs Float division

* Float division of integers: Multiply with 1.0 or cast into float. 

* Left to right associative: ```a/b/c```  <=>```(a/b)/c```

* Variable updates: 

  * x = x +1, 

  * ++, --: pre/post 

    * x++: use x, then increment its value
    
    * ++x: increment x, then use updated value
    
    * ```c
      #include <stdio.h>
      #include <stdlib.h>
      
      int main() {
      	int x = 5;
      	printf("%d ", x--); // Prints 5
      	printf("%d ", x); // Prints 4
      	printf("%d", ++x); // Prints 5 
      	return 0;
      }
      ```

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

### Question 1

Write a program that takes three integer from user and calculates the sum of the numbers which cannot be divided by 3.  (Use relational operator)

```
input: 1 3 5
output: 6

input: 2 7 1
output: 10
```

## Data Type: Char

- Represent characters (letters, digits, signs)

- 1 byte = 8 bits = 256 values.

- Syntax: `char ch = 'a';`

- Identifier: `%c`

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
  
  - ```c
    #include <stdio.h>
    #include <stdlib.h>
    
    int main() {
    	char ch = 'D';
    
    	printf("%c ", ch); // Prints D
    	printf("%d ", ch); // Prints 68 (corresponding integer value of D) 
    	printf("%d ", ch - 2); // Prints 66
    	printf("%c", ch - 2); // Prints B (character corresponding to 66)
    	return 0;
    }
    ```

### Question 2

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

### Question 3

Write a program to convert height from centimeters to feet.

```
define constants: 
INCHES_IN_FOOT = 12 // 1 foot = 12 inches 
CM_IN_INCH=2.54 // 1 inch = 2.54 cms 
height in cm, read from user

input: 180
output: 5.9055
```

### Question 4

Write a program that reads one character as input and print 1 if it is a digit else 0. 

```
input: 7
output: 1

input: a
output: 0
```

## References

* https://www.geeksforgeeks.org/errors-in-cc/

* https://www.commfront.com/pages/ascii-chart

* https://fresh2refresh.com/c-programming/c-operators-expressions/c-relational-operators/

  