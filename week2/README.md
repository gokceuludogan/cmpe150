# Cmpe150.03 Week 2

## Summary of Last Week

### Output

```c 
#include <stdio.h>
int main()
{
    printf("Hello world!");
	return 0;    
}
```

### Integer variables

```c 
#include <stdio.h>
int main()
{
    int number_1, number_2, sum;
    number_1 = 3;
    number_2 = 5;
    sum = number_1 + number_2;
    printf("Number1: %d Number2: %d Sum: %d \n", number_1, number_2, sum);
	return 0;    
}
```

### Puts vs Printf

* Puts function is used for displaying only *strings (text).*

* Printf function is able to display *strings and variables*.

  ![1569961731136](figures/1569961731136.png)

  
  
  

------

### Variable names

* It can contain alphanumeric characters and underscore(_)
* It cannot start with number.
* Case-sensitive.

###  Warm Up

Write a program that prints the following shape to the screen using only *printf()*.

```
*   *  
 * *   
  *    
 * *   
*   *  
```

or 

Write a  program that prints a block F using hash (#), where the F has a height of six characters and width of five and four characters.

```
######
#
#
#####
#
#
#
```

### Getting Input: Scanf()

* Format: ```scanf("%d", &number);```  *the variable **number** must be declared before.*
* Requires  *stdio.h*: ```#include <stdio.h>```

```c
#include <stdio.h>
int main(){
    // Declare variables
    int number_1, number_2, product;
    //Read first value
    printf("Enter first number\n");
    scanf("%d", &number_1);
    //Read second value
    printf("Enter second number\n");
    scanf("%d", &number_2);
    product = number_1 * number_2;
    // Display output
    printf("The product of %d and  %d is %d\n", number_1, number_2, product);
    return 0;
}
```

### Bit vs Byte

* **Bit:** the smallest unit, *0 or 1*.
* **Byte:** a collection of bits: *8 bits.* *(i.e. 01010111)* 

### Fundamental Data Types

![img](https://qph.fs.quoracdn.net/main-qimg-7852cd4b11648b9ec8029a5df338bc2b)



| Type                     | Size (bytes)                  | Format Specifier |
| :----------------------- | :---------------------------- | :--------------: |
| `int`                    | at least 2, usually 4         |       `%d`       |
| `char`                   | 1                             |       `%c`       |
| `float`                  | 4                             |       `%f`       |
| `double`                 | 8                             |      `%lf`       |
| `short int`              | 2 usually                     |      `%hd`       |
| `unsigned int`           | at least 2, usually 4         |       `%u`       |
| `long int`               | at least 4, usually 8         |      `%li`       |
| `long long int`          | at least 8                    |      `%lli`      |
| `unsigned long int`      | at least 4                    |      `%lu`       |
| `unsigned long long int` | at least 8                    |      `%llu`      |
| `signed char`            | 1                             |       `%c`       |
| `unsigned char`          | 1                             |       `%c`       |
| `long double`            | at least 10, usually 12 or 16 |      `%Lf`       |

### Integer Representation

<img src="https://www.allaboutcircuits.com/uploads/articles/TwoComplementCircleV2.jpg" alt="Image result for two's complement" style="zoom: 50%;" />

#### Two's Complement

* Leftmost bit represents the sign (0 for positive, 1 for negative).
* If positive, value is the numeric value of the remaining binary pattern.
* If negative, value is the numeric value of the complement(\*) of the remaining binary pattern, plus one. (*) complement: Switch 0's to 1's, and vice versa.
* Example: 0 100 0001
  * Sign bit is 0 ⇒ positive.
  * Absolute value is 100 0001B = 65D (D: Decimal; B: Binary)
  * The represented value is +65D
* Example: 1 000 0001
  * Sign bit is 1 ⇒ negative
  * Absolute value is the complement of 000 0001B plus 1, i.e., 111 1110B + 1B = 127D
  * Hence, the represented value is -127D

------

* If an integer type is stored in N bits
  * Signed range: -2^(N-1) and 2^(N-1) -1
  * Unsigned range: 0 to 2^N - 1.
  * Example: int: 4 bytes = 32 bits
    * int: - 2^(31) and 2^(31) -1.
    * unsigned int: 0 and 2^(32) - 1.
* The sizeof() function returns the number of bytes occupied by each type. Returns *long*, so the identifier: *%lu*

#### Overflow: Outside of the range.

```c 
#include <stdio.h>
int main()
{
    // the sizes of data types
    printf("size of char = %lu\n", sizeof(int));
    printf("size of char = %lu\n", sizeof(long));
    printf("size of char = %lu\n", sizeof(unsigned int));
    int a; // declaration
    a = 2147483647; // assignment of largest int
    printf("%d\n", a+1);
    return 0;
}
```

### Floating Point Representation

Stores nonintegers. 

|    Type     | Storage size |      Value range       |     Precision     |
| :---------: | :----------: | :--------------------: | :---------------: |
|    float    |    4 byte    |   1.2E-38 to 3.4E+38   | 6 decimal places  |
|   double    |    8 byte    |  2.3E-308 to 1.7E+308  | 15 decimal places |
| long double |   10 byte    | 3.4E-4932 to 1.1E+4932 | 19 decimal places |

### Q1

Write a C program that reads the radius of a sphere and calculates the volume. *(π: 3.14)*
$$
V = 4/3*π*r^3
$$


* **Input**: 3.5 **Output**: 179.50



### Q2

Write a program that converts a temperature from  Fahrenheit to Centigrade.
$$
C = (5/9) * (F - 32)
$$


* Example input and outputs: 
  * F: 32.0 	C: 0
  * F: 212.0   C: 100
  * F: 140.0   C: 60 

### Q3

 Write a program to convert a given integer (in seconds) to hours, minutes and seconds.

* **Input**: 25300                                                   
* **Output:** H:M:S - 7:1:40

### Q4

Write a program to find the third angle of a triangle if two angles are given with getting input in one line separated by a comma.

* **Input:** 80,30
* **Output:** 70