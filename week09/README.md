# Week 9 - Arrays

<details><summary>Brief Summary</summary>
    <p><img src='https://raw.githubusercontent.com/hkmztrk/CMPE150/5a68414c5a77b913cd253a240b734e594b25e8f3/week09/W09_01.PNG'/></p>
<p><img src='https://raw.githubusercontent.com/hkmztrk/CMPE150/5a68414c5a77b913cd253a240b734e594b25e8f3/week09/W09_02.PNG'/></p>
<p><img src='https://raw.githubusercontent.com/hkmztrk/CMPE150/5a68414c5a77b913cd253a240b734e594b25e8f3/week09/W09_03.PNG'/></p> </details>

## Question 1 (Teaching Codes PS11)

**a**. Write a program that reads an integer N from the user, then reads N more integers from the user and store them in an array. Then prints the sum and average of the elements.

| Input                         | Output      |
| ----------------------------- | ----------- |
| 10 <br />1 2 3 4 5 6 7 8 9 10 | 55 5.500000 |
| 4<br />4 1 3 8                | 16 4.000000 |

**b**. Write a program that reads 10 elements from the user and store them in an array. Then prints elements larger than the average of numbers held in the array. 

| Input                          | Output     |
| ------------------------------ | ---------- |
| 10  <br />1 2 3 4 5 6 7 8 9 10 | 6 7 8 9 10 |
| 4 <br />4 1 3 8                | 8          |

## Question 2 (Teaching Codes Lab7)

Write a program which reads a sentence from the user (read characters until '\n' appears). Your program then should put this sentence into a char array (assume the sentence will be shorter than 50 characters).

Then, encrypt this sentence by adding +1 to the value of each character and print the encrypted version to the screen.

Then decrypt this sentence by adding -1 to each character, and print the decrypted version  to the screen.

| Input          | Output                            |
| -------------- | --------------------------------- |
| Hello Bogazici | Ifmmp!Cphb{jdj<br/>Hello Bogazici |
| Stay at home   | Tubz!bu!ipnf<br/>Stay at home     |

## Question 3 (Teaching Codes Lab7)

**a**. Write a program which reads an integer N from the user, then reads N integers from the user and store them in an array. Then print them to the screen in reverse order. Assume N is smaller than 50.

**b.** Write a program which reads an integer N from the user, then reads N integers from the user and store them in an array.  Then reverse the order of these integers in the array and print the array. 

| Input                 | Output         |
| --------------------- | -------------- |
| 5<br />3 1 -4 5 2     | 2 5 -4 1 3     |
| 6<br />15 7 2 89 8 12 | 12 8 89 2 7 15 |

## Question 4 (Teaching Codes Lab7)

Write a program which reads two integers: N and M from the user. Then the program should read N more integers, then M more integers from the user. Assume N < M < 50.

If the first combination of N integers appears at least once in the second combination of M integers, the program should write the starting index of the first appearance in the second combination. Otherwise it should not print anything.

| Input                                          | Output |
| ---------------------------------------------- | ------ |
| 4 12<br/>4 5 6 5<br/>1 2 1 2 99 99 4 5 6 5 9 9 | 6      |
| 3 5<br/>2 2 2<br/>1 2 2 2 5                    | 1      |
| 3 5<br/>2 3 2<br/>1 2 2 2 5                    |        |

## Question 5 

Write a program which reads an integer N from the user, then reads N integers from the user to an array. Then find frequency of each element in the array. Assume N is smaller than 1000 and the entered numbers will be between 0 and 100 (inclusive).

| Input                         | Output                                     |
| ----------------------------- | ------------------------------------------ |
| 10<br/>5 10 2 5 50 5 10 1 2 2 | 1: 1<br/>2: 3<br/>5: 3<br/>10: 2<br/>50: 1 |

## Question 6

**a.** Write a program reads two integers N1, N2 from the user, then reads N1 and N2 integers from the user to create two arrays. Then print common (included in both arrays) elements and their indices in the first array. 

| Input                                          | Output                     |
| ---------------------------------------------- | -------------------------- |
| 6 8<br/>2 5 10 53 17 8<br/>-1 6 5 87 2 17 49 7 | 2 0<br/>5 1<br/>17 4<br /> |

**b.** Update or rewrite your program so that if the common element is included twice or more in the second array, print the common element and its index in the first array once. 

| Input                                           | Output               |
| ----------------------------------------------- | -------------------- |
| 6 8<br/>2 5 10 53 17 8<br/>-1 6 5 87 2 17 49 17 | 2 0<br/>5 1<br/>17 4 |

## Question 7

Write a program which reads an integer N from the user, then reads N integers from the user to an array. Then modify the array so that it contains exactly the same numbers as the given array, but rearranged so that every 3 is immediately followed by a 4. Do not move the 3's, but every other number may move. The array contains the same number of 3's and 4's, every 3 has number after it that is not a 3, and a 3 appears in the array before any 4.

| Input           | Output        |
| --------------- | ------------- |
| 4 1 3 1 4       | 1 3 4 1       |
| 7 1 3 1 4 4 3 1 | 1 3 4 1 1 3 4 |
| 4 3 2 2 4       | 3 4 2 2       |