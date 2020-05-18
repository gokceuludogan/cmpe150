# Cmpe150 Week12

## Question 1 - Is symmetric?

Write a program reads an integer N from the user, then reads N integers from the user. Then checks whether the array is symmetric. 

| Input                    | Output        |
| ------------------------ | ------------- |
| 7<br />10 3 -1 5 -1 3 10 | symmetric     |
| 5<br />1 3 5 2 0         | not symmetric |

## Question 2 - Successively Repeating 

Write a program reads an integer N from the user. Takes N integers from user and place them in an array. Then, print the maximum number of repeating elements successively and this repeating element. 

| Input                            | Output |
| -------------------------------- | ------ |
| 7<br/>10 2 4 4 5 5 5             | 3 5    |
| 13<br/>8 8 8 8 2 2 4 4 4 5 5 2 9 | 4 8    |

**a.** First, find the successive occurrences of all elements and then print the element and number of successive occurrences of that. 

| Input                            | Output                                      |
| -------------------------------- | ------------------------------------------- |
| 13<br/>8 8 8 8 2 2 4 4 4 5 5 2 9 | 4 8<br/>2 2<br/>3 4<br/>2 5<br/>1 2<br/>1 9 |

**b.** Now you have the successive occurrences of elements. Find maximum of them.

| Input                             | Output                                                       |
| --------------------------------- | ------------------------------------------------------------ |
| 13<br />8 8 8 8 2 2 4 4 4 5 5 2 9 | 4 8<br />2 2<br />3 4<br />2 5<br />1 2<br />1 9<br />Max: 4 8 |

## Question 3 - Array with Pointer

Create a one dimensional array in the main function and initialize it with some integers. Then print the content of the array and the address of the each cell of the array using pointers. In other words, you are not allowed to use ``[ ]`` operators inside the loop you have written. You can use the size of the array in the loop you have written.

| Example Output                                               |
| ------------------------------------------------------------ |
| 1 0x7ffee72153c0<br /> 2 0x7ffee72153c4<br /> 3 0x7ffee72153c8<br /> 4 0x7ffee72153cc<br /> 5 0x7ffee72153d0 |

## Question 4 - Shift the Array

Write a function called **rightShiftA()** that takes the size of the array (N), an integer array (arr) and an integer variable (T) as parameters. The function right shifts the array T times.

Write a proper main function to see the effect of **rightShiftA()**.

| Input                 | Output    |
| --------------------- | --------- |
| 5 <br>1 2 3 4 5 <br>3 | 3 4 5 1 2 |
| 4 <br>1 2 3 4 <br>10  | 3 4 1 2   |

## Question 5 - Interstellar

Given a 4x4 matrix consisting of * and lowercase English alphabets, the task is to find the character which has the maximum number of * around it (including diagonal elements too). If two characters have same maximum count, print lexicographically smallest character.

| Input                                                       | Output |
| ----------------------------------------------------------- | ------ |
| b\*\*\* <br/>\*\*c\*       <br/>\*a\*\*       <br/>\*\*\*d  | a      |
| \*r\*\*      <br/>maz\*       <br/>l\*fk       <br/>\*\*\*d | f      |

## Question 6 - Put My Words

Write a program which reads a **sentence (string)**  a **word (string)** and a **positive integer number (int)**. Insert the word to the sentence as the given numbered word. Then the modified sentence will be printed.

A sentence consists of words separated by spaces. There will be at least one word in a sentence. There will be exactly one space between each word in a sentence. A word consists of only letters (both lowercase and uppercase is possible). A sentence cannot be longer than 1000 characters. A word cannot be longer than 20 letters. The number can't be larger than the number of words in the sentence + 1.

**Reminder:** A string is a char array that has \0 character at the end.

**Reminder 2:** There shouldn’t be spaces or new lines at the end or the beginning of the sentence.


| Input                                              | Output                                   |
| -------------------------------------------------- | ---------------------------------------- |
| is my life now <br>1 <br>this                      | this is my life now                      |
| WHeN LiFe GiVeS You MaKe LeMoNaDe <br>5 <br>LeMoNs | WHeN LiFe GiVeS You LeMoNs MaKe LeMoNaDe |
| dont Wait for <br>4 <br>Opportunity                | dont Wait for Opportunity                |

## Question 7 - Remove Non-Letters

Write a program that takes a string from the user and removes the characters the non-letter characters. Of course the null character ``\0`` should stay. 

| Input        | Output |
| ------------ | ------ |
| h3ll0 w0r1d! | hllwrd |
| 2020 may 19  | may    |

