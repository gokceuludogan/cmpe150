# Cmpe150 Week 11

## Multidimensional Arrays

*  An array of arrays

  ```c
  type name[size1][size2]...[sizeN];
  ```

  

* Two dimensional

  ```c
  float x[3][4];
  ```

  ![Two dimensional array in C programming](https://cdn.programiz.com/sites/tutorial2program/files/two-dimensional-array_0.jpg)

* Three dimensional

  ```c
  float y[2][4][3];
  ```

* Initialization

  ```c
  int c[2][3] = {{1, 3, 0}, {-1, 5, 9}};
           
  int c[][3] = {{1, 3, 0}, {-1, 5, 9}};
                  
  int c[2][3] = {1, 3, 0, -1, 5, 9};
  ```

* Setting a column

  ```
  for(int column=0; column < col_size; column++)
  	a[1][column] = -1;
  ```

* Setting a row

  ```
  for(int row=0; row < row_size; row++)
  	a[row][0] = 1;
  ```

#### Warm up

Write a program which reads two integers corresponding the sizes of a two dimensional array and then reads this array. 

```
3 5
18 3 5 2 4
1 4 0 9 5
2 -1 7 12 8
```

#### Question 1

Write a program which takes a two dimensional array and prints its transpose. 

```
input: 
3 5
18 3 5 2 4
1 4 0 9 5
2 -1 7 12 8
output:
18 1 2
3 4 -1
5 0 7
2 9 12
4 5 8
```

### Passing 2-D arrays to functions

Sizes are given inside parentheses. 

```type func_name(int m, int n, int arr[m][n])```

Calling function with 2-d array, similar to one dimensional arrays:

```
int arr[2][3] = {0};
func_name(size1, size2, arr);
```

### Question 2

Write a function named **print_2d_array()** which takes the sizes of 2d array and an array as parameters and prints it.

Write a function named **read_2d_array()** which takes the sizes of 2d array and an array as parameters and reads it from user into this array.

### Question 3

Write a program to find sum of left and right diagonals of a two dimensional array

```
input: 
3 3
1 5 3
4 8 6
2 10 7
output:
16 // left diagonal: 1 + 8 + 7
13 // right diagonal: 3 + 8 + 2
```

### Question 4

Write a program to find the sum of lower triangular elements of a two dimensional array.

```
input:
3 3 
1 5 3
4 8 6
2 10 7
output:
16 // 4 + 2 + 10
```

### Homework 

Write a program that plays tic-tac-toe. The tic-tac-toe game is played on a 3x3 grid the game is played by two players, who take turns. The first player marks moves with a 0, the second with a 1 . The player who has formed a horizontal, vertical, or diagonal sequence of three marks wins.  Your program should draw the game board, ask the user for the coordinates of the next mark, change the players after every successful move, and pronounce the winner.

```
Sample input and outputs // Assume player 1 starts first. Then they take turns during game.
Before player makes a move, show the current status of the board to user. 
| | | | 
| | | |
| | | |
Assume that board is marked from 1 to 9 as folows: 
|1|2|3| 
|4|5|6|
|7|8|9|
Read player 1's move, place it and show. 
5 // Player 1 made a move. 
After each move, check any of the winning condition is satisfied. if so, pronounce winner. otherwise, show board and read the other player's move. 
| | | | 
| |0| |
| | | |
1 // Player 2 made a move.
|1| | | 
| |0| |
| | | |
3 // Player 1 made a move.
|1| |0| 
| |0| |
| | | |
7 // Player 2 made a move.
|1| |0| 
| |0| |
|1| | |
4 // Player 1 made a move.
|1| |0| 
|0|0| |
|1| | |
6 // Player 2 made a move.
|1| |0| 
|0|0|1|
|1| | |
8 // Player 1 made a move.
|1| |0| 
|0|0|1|
|1|0| |
2 // Player 2 made a move.
|1|1|0| 
|0|0|1|
|1|0| |
9 // Player 1 made a move.
|1|1|0| 
|0|0|1|
|1|0|0|
The board is full and winning condition is not satisfied after any of moves. So, it is a tie. Then, announce it. 
```

## References

https://www.programiz.com/c-programming/c-multi-dimensional-arrays

http://www.cprogrammingnotes.com/question/tic-tac-toe-game.html

