# Solutions

## Warm up

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {
	int row, col;
	scanf("%d %d", &row, &col);

	int numbers[row][col];
    int i, j;
	for(i=0; i<row; i++){
		for(j=0;j<col;j++){
			scanf("%d", &arr[i][j]);
		}
	}
    return 0;
}
```

## Question 1

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {
	int row_size, col_size, i, j;
	scanf("%d %d", &row_size, &col_size);
	int matrix[row_size][col_size];

	for(i=0; i<row_size; i++){
		for(j=0; j<col_size; j++){
			scanf("%d", &matrix[i][j]);
		}
	}

	for(j=0; j<col_size; j++){
		for(i=0; i<row_size; i++){
			printf("%d ", matrix[i][j]);
		}
		printf("\n");
	}
	return EXIT_SUCCESS;
}
```

## Question 2

```c
#include <stdio.h>
#include <stdlib.h>

void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0;j<n;j++){
			scanf("%d", &arr[i][j]);
		}
	}
}


void print_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0;j<n;j++){
			printf("%d ", arr[i][j]);
		}
		printf("\n");
	}
}

int main(void) {
	int row, col;
	scanf("%d %d", &row, &col);

	int numbers[row][col];
	read_2d_array(row, col, numbers);
	print_2d_array(row, col, numbers);
    return 0;
}
```

## Question 3

```c
#include <stdio.h>
#include <stdlib.h>

void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0;j<n;j++){
			scanf("%d", &arr[i][j]);
		}
	}
}

int sum_left_diagonal(int size, int arr[size][size]){
	int i, sum=0;
	for(i=0; i<size; i++){
		sum += arr[i][i];
	}
	return sum;
}

int sum_right_diagonal(int size, int arr[size][size]){
	int i, sum=0;
	for(i=0; i<size; i++){
		sum += arr[i][size-i-1];
	}
	return sum;
}

int main(void) {
	int size1, size2;
	scanf("%d %d", &size1, &size2);
	int numbers[size1][size2];
	read_2d_array(size1, size2, numbers);
	int left_diag = sum_left_diagonal(size1, numbers);
	int right_diag = sum_right_diagonal(size1, numbers);

	printf("%d\n%d", left_diag, right_diag);
    return 0;
}    
```

### Inside main

```c
#include <stdio.h>
#include <stdlib.h>

void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0;j<n;j++){
			scanf("%d", &arr[i][j]);
		}
	}
}

int main(void) {
	int row, col;
	scanf("%d %d", &row, &col);
	int numbers[row][col];
	read_2d_array(row, col, numbers);
	int sum = 0;
	int i;
	for(i=0; i<row; i++){
    	sum += numbers[i][i];
    }
    printf("%d\n", sum);
    sum=0;
    for(i=0; i<row; i++){
    	sum+= numbers[i][row-i-1];
    }
    printf("%d\n", sum);
	return 0;
}    
```

## Question 4

```c
#include <stdio.h>
#include <stdlib.h>

void read_2d_array(int m, int n, int arr[m][n]){
	int i, j;
	for(i=0; i<m; i++){
		for(j=0;j<n;j++){
			scanf("%d", &arr[i][j]);
		}
	}
}

int main(void) {
	int row, col;
	scanf("%d %d", &row, &col);
	int numbers[row][col];

	read_2d_array(row, col, numbers);

	int sum = 0;
	int i, j;
	for(i=0; i<row; i++){
		for(j=0; j<col; j++){
			if(i > j){
				sum += numbers[i][j];
			}
		}
	}
	printf("%d", sum);
	return EXIT_SUCCESS;
}

```

### As a function

```c
int sum_left_triangle(int size, int arr[size][size]){
	int i, j, sum = 0;
	for(i=0; i<size; i++){
		for(j=0;j<size; j++){
			if(i > j){
				sum += arr[i][j];
			}
		}
	}
	return sum;
}
```

## Homework :eyes:

The solution seems a bit long but don't be afraid! Most of the lines are for printing a prettier board for you! Besides, the code works for variable board size.

```c
#include <stdio.h>
#include <stdlib.h>
#include <teachingcodes.h>

#define BOARD_SIZE 4
#define player1 0
#define player2 1

/*
 * Checks board for the winner
 */
int check_winner(int board[BOARD_SIZE][BOARD_SIZE]){
	int i, j, row_sum=0, col_sum=0, left_diag_sum=0, right_diag_sum=0;
	for(i=0; i<BOARD_SIZE; i++){
		for(j=0; j<BOARD_SIZE; j++){
			row_sum += board[i][j] == -1 ? BOARD_SIZE+1 : board[i][j];
			col_sum += board[j][i] == -1 ? BOARD_SIZE+1 : board[j][i];
		}
		//printf("%d %d %d\n", i, row_sum, col_sum);
		if(row_sum == BOARD_SIZE || col_sum == BOARD_SIZE){
			return 1;
		}else if(row_sum == 0 || col_sum == 0){
			return 0;
		}
		row_sum=0;
		col_sum=0;
		left_diag_sum += board[i][i] == -1 ? BOARD_SIZE+1 : board[i][i];
		right_diag_sum += board[i][BOARD_SIZE-i-1] == -1 ? BOARD_SIZE+1 : board[i][BOARD_SIZE-i-1];
	}
	//printf("%d %d\n", left_diag_sum, right_diag_sum);
	if(left_diag_sum == BOARD_SIZE || right_diag_sum == BOARD_SIZE){
		return 1;
	}else if(left_diag_sum == 0 || right_diag_sum == 0){
		return 0;
	}
	return -1;
}

/*
 * Simple and ugly board
 */
void print_simple_board(int board[BOARD_SIZE][BOARD_SIZE]){
	printf("Player 1 (%d)  -  Player 2 (%d)\n\n", player1, player2);
	int i, j;
	for(i=0; i<BOARD_SIZE; i++){
    	for(j=0; j<BOARD_SIZE; j++){
    		if(board[i][j] == -1){
    			printf("-");
    		}else{
    			printf("%d", board[i][j]);
    		}
    	}
    	printf("\n");
    }
}

/*
 * Separator used for pretty board
 */
void print_separator(char ch){
	int j;
	for(j=0; j <BOARD_SIZE; j++){
		printf("%c%c%c", ch, ch, ch);
		if(j != BOARD_SIZE-1){
			printf("|");
		}
	}
}

/*
 * Big and nice board
 */
void print_board(int board[BOARD_SIZE][BOARD_SIZE]){
	printf("Player 1 (%d)  -  Player 2 (%d)\n\n", player1, player2);
	int i, j;
	for(i=0; i<BOARD_SIZE; i++){
		print_separator(' ');
		printf("\n");
		for(j=0; j <BOARD_SIZE; j++){
			if(board[i][j] == -1){
				printf("   ");
			}else{
				printf(" %d ", board[i][j]);
			}
			if(j != BOARD_SIZE-1){
				printf("|");
			}
		}
		if(i != BOARD_SIZE-1){
			printf("\n");
			print_separator('_');
			printf("\n");
		}
	}
	printf("\n");
	print_separator(' ');
	printf("\n");
}

int main(void) {
	setbuf(stdout, NULL);
	int board[BOARD_SIZE][BOARD_SIZE];
	int i, j;
	for(i=0; i<BOARD_SIZE; i++){
		for(j=0; j<BOARD_SIZE; j++){
			board[i][j] = -1; // Initialize array elements with -1
		}
	}

	int moves=0, choice;
	print_board(board);
	while(1){
		printf("Player %d's turn: ", moves%2 + 1);
		scanf("%d", &choice); //1, 2, 3, ..., BOARD_SIZE*BOARD_SIZE
		int row = (choice - 1) / BOARD_SIZE;
		int col = (choice - 1) % BOARD_SIZE;
		while(choice > BOARD_SIZE*BOARD_SIZE || choice < 1 || board[row][col] != -1){
			printf("Not valid! Make a valid move!");
			scanf("%d", &choice);
			row = (choice - 1) / BOARD_SIZE;
			col = (choice - 1) % BOARD_SIZE;
		}
		board[row][col] = moves % 2;
		print_board(board);
		moves++;
		int winner = check_winner(board);
		if(winner == -1 && moves == BOARD_SIZE*BOARD_SIZE){
			printf("It's a tie!");
			break;
		}else if(winner == 1){
			printf("Player 2 won!");
			break;
		}else if(winner == 0){
			printf("Player 1 won!");
			break;
		}
	}
	return EXIT_SUCCESS;
}
```

