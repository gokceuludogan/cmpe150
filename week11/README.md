# Cmpe150 Week11

## Strings

* character array. `char str[101];`
* ends with the null character ('\0').
* `char str[] = "Hello";` = `char str[] = {'H', 'e', 'l', 'l', 'o', '\0'};`

**Single quotes for characters, double quotes for strings!**

* No need to track size of it. 

  * ```c
    char str[] = "Hello World!";
    for(int i=0; str[i] != '\0'; i++)
    	printf("%c-", str[i]);
    ```

### Output

* `printf("%s\n", str);`  =  `puts(str);`

### Input

* `char str[101];`

* `gets(str); // Reads until enter`

* `scanf("%s", str); // Reads until space`

* **Safer**: `fgets(str, 21, stdin);`


### Passing strings to functions

* Same as arrays: pass by reference.
* No need to pass the size. 

### Built-in string library

* #include <string.h>
* strlen(): Length of a string
  * The size of a string, not counting the terminating zero '\0'.
* strcpy() and strncpy(): Copy strings
  * `char *strcpy(char *s1, const char *s2); `
  * `char *strncpy(char *s1, const char *s2, size_t n)`
* strcmp() and strncmp(): Compare strings
  * `int strcmp(const char *s1, const char *s2);`
    * Returns < 0 if s1 comes before s2 alphabetically.
    *  Returns 0 if s1 is identical to s2 alphabetically.
    * Returns > 0 if s1 comes after s2 alphabetically.
  * `int strncmp(const char *s1, const char *s2, size_t n);`
* strcat(), strncat(): Append a string to the end of another
  * `char *strcat(char *s1, const char *s2);`
  * `char *strncat(char *s1, const char *s2, size_t n);`

### Question 1

Write a function that copies a source string to the destination string. You can assume that (you should ensure that) destination string is large enough.

*Try using `strcpy` function from `string.h` library.*

### Question 2

Write a function that takes two strings as argument and compares them. The function should perform what `strcmp` function from `string.h` library. Validate your function by using `strcmp` along with your function.

```
input: abz abc 
output: 23
```

### Question 3

Write a program to count the total number of words in a string.

```
input: count the total number of words in a string
output: 9
```

### Question 4

**a.** Write a program which takes a string and an integer n as parameters and print the nth word in the string. 

```
input: count the total number of words in a string 3
output: total
```

**b. **Write a program which takes a string and an integer n as parameters and deletes the nth word in the string. 

```
input: count the total number of words in a string. 3
output: count the number of words in a string.
```

### Question 5

**a.** Write a program to find maximum occurring character in a string assume all characters in lowercase.

```
input: she borrowed the book
output: o
```

**b.** Update your program so that it would work with all characters not only lowercase ones.

*Hint: What's the size of ASCII table?*

### Question 6

Write a program which reads a sentence as a string, and a word as a string. Then the program should exclude this word from the sentence if the sentence contains the word, then print the new version to the screen. Assume no punctuation will occur, and every letter is lower case.

```
input: merhaba dunyali nasilsin dunyali
output: merhaba nasilsin
```

### Question 7

Write a program which takes a string as parameter and sorts words of this string and prints the resulting string. Assume initial string has maximum 100 characters and the length of each word is at most 10. 

```
input: the lake is a long way from here
output: a from here is lake long the way
```

