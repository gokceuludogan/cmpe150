# Cmpe150 Week12

## Warm up

From: https://github.com/hkmztrk/CMPE150/tree/master/W11

Write a program reads a 2D array and an integer k. Print this array following the pattern below:

For the first row, print first k elements and sum of them.
For the second row, print first 2k elements and sum of them.
For the third row, print first 3k elements and sum of them.

Apply this for all rows.
If x_k becomes higher then the row size, print and sum all elements in the row.

```
Input:
3 11 3
8 5 2 5 6 7 2 0 1 4 7
9 6 3 8 1 4 0 3 2 7 5
7 6 4 3 5 2 4 8 0 9 4

Output:
8 5 2 15
9 6 3 8 1 4 31
7 6 4 3 5 2 4 8 0 39

Input: 
4 7 3
1 2 3 4 5 6 7
1 2 3 4 5 6 7
1 2 3 4 5 6 7
1 2 3 4 5 6 7

Output:
1 2 3 6
1 2 3 4 5 6 21
1 2 3 4 5 6 7 28
1 2 3 4 5 6 7 28
```

## Strings

* character array. `char str[101];`
* ends with the null character ('\0').
* `char str[] = "Hello";` = `char str[] = {'H', 'e', 'l', 'l', 'o', '\0'};`
  * Size of this array?

**Single quotes for characters, double quotes for strings!**

* No need to track size of it. 

  * ```
    char str[] = "Hello World!";
    for(int i=0; str[i] != '\0'; i++)
    	printf("%c-", str[i]);
    ```

### Output

* `printf("%s\n", str);`  =  `puts(str);`

### Input

* `char str[101];`

* `gets(str);`

* `scanf("%s", str);`

* **Safer**: `fgets(str, 21, stdin);`

* ```c
  char str[100], name[20], surname[20];
  int age;
  gets(str);
  sscanf(str, "%s %s %d", name, surname, &age);
  printf("Name: %s Surname: %s Age: %d", name, surname, age);
  ```

### Passing strings to functions

* Same as arrays: pass by reference
* No need to pass the size

### Built-in string library

* #include <string.h>
* strlen(): Length of a string
  * The size of a string, not counting the terminating zero '\0'.
  * Type: size_t (defined as unsigned long, formatter: %lu)
* strcpy() and strncpy(): Copy strings
  * `char *strcpy(char *s1, const char *s2); `
  * `char *strncpy(char *s1, const char *s2, size_t n)`
  * 
* strcmp() and strncmp(): Compare strings
  * `int strcmp(const char *s1, const char *s2);`
    * Returns < 0 if s1 comes before s2
    *  Returns 0 if s1 is identical to s2.
    * Returns > 0 if s1 comes after s2
  * `int strncmp(const char *s1, const char *s2, size_t n);`
* strcat(), strncat(): Append a string to the end of another
  * `char *strcat(char *s1, const char *s2);`
  * `char *strncat(char *s1, const char *s2, size_t n);`

### Homework

Implement the abovementioned functions yourself!

### Question 1

Write a program to count the total number of words in a string.

```
input: count the total number of words in a string.
output: 9
```

### Question 2

Write a program which takes a string and an integer n as parameters and print the nth word in the string. 

```
input: count the total number of words in a string. 3
output: total
```

####  Homework

 Write a program which takes a string and an integer n as parameters and deletes the nth word in the string. 

```
input: count the total number of words in a string. 3
output: count the number of words in a string.
```

### Question 3

Write a program to find maximum occurring character in a string assume all characters in lowercase.

```
input: she borrowed the book
output: o
```

#### Homework

Update your program so that it would work with all characters not only lowercase ones.

*Hint: What's the size of ASCII table?*

### Homework

Write a program which takes a string as parameter and sorts words of this string and prints the resulting string. Assume initial string has maximum 100 characters and the length of each word is at most 10. 

```
input: the lake is a long way from here
output: a from here is lake long the way
```

### Question 4

Write a program which takes two strings as parameters and check whether the second string is present in the first string. If it's present, print the starting index of the second string in the first string. Otherwise, print -1.

```
input: 
A thousand years in the future
years
output: 11
input: 
A thousand years in the future
class
output: -1
```

### Homework

Write a program to trim both leading and trailing whitespace characters in a string. **Leading space** is all whitespace at the beginning of a line while **trailing space** is all **whitespace** located at the end of a line, without any other characters following it. 

```
input:
         	  Be careful. There are white spaces at the beginning and the end of this string!       
output: 
Be careful. There are white spaces at the beginning and the end of this string!
```

