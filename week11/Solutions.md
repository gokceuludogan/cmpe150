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

Stay tuned!  Solution will be here on Tuesday night or maybe sooner!

*Note: To solve reading all inputs before printing any, put the following statement inside main function: `	setbuf(stdout, NULL);`*

