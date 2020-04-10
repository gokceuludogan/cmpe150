# Solutions

## Question 1

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int number, i, sum_of_fact=0;
	scanf("%d", &number);
	while(1){
		int last_digit = number % 10;
		int factorial = 1;
		for(i = 2; i <= last_digit; i++){
			factorial *= i;
		}
		sum_of_fact += factorial;
		number /= 10;
		if(number == 0){
			break;
		}
	}
	printf("%d", sum_of_fact);
	return 0;
}
```

### Alternative

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int number, i, sum_of_fact=0;
	scanf("%d", &number);
	while(number > 0){
		int last_digit = number % 10;
		int factorial = 1;
		for(i = 2; i <= last_digit; i++){
			factorial *= i;
		}
		sum_of_fact += factorial;
		number /= 10;
	}
	printf("%d", sum_of_fact);
	return EXIT_SUCCESS;
}
```

## Question 2

### a.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int number, i, is_prime = 1;
	scanf("%d", &number);
	for(i = 2; i < number; i++){
		if(number % i == 0){
			is_prime = 0;
			break;
		}
	}

	if(is_prime){
		printf("prime");
	}else{
		printf("not prime");
	}
	return 0;
}

```

### b.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int number, i, j;
	scanf("%d", &number);
	for(i = 2; i< number; i++){
		int is_prime = 1;
		for(j = 2; j < i; j++){
			if(i % j == 0){
				is_prime = 0;
				break;
			}
		}
		if(is_prime){
			printf("%d ", i);
		}
	}
	return 0;
}

```

## Question 3

### a.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N, M, i, j;
	scanf("%d%d", &N, &M);

	for(i = 0; i < N; i++){
		for(j = 0; j < M; j++){
			printf("*");
		}
		printf("\n");
	}
	return 0;
}
```

### b.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N, M, i, j;
	scanf("%d%d", &N, &M);

	for(i = 0; i < N; i++){
		for(j = 0; j < M; j++){
			if(i == 0 || j == 0 || i == N -1 || j == M - 1){
				printf("*");
			}else{
				printf("-");
			}

		}
		printf("\n");
	}
	return 0;
}

```

## Question 4

### a.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int number, i, j;
	scanf("%d", &number);
	for(i = 1; i <= number; i++){
		for(j = 1; j <= i; j++){
			printf("%d", j);
		}
		printf("\n");
	}
	return 0;
}
```

### b.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int row, number, i, j;
	scanf("%d%d", &row, &number);
	for(i = 1; i <= row; i++){
		int power = 1;
		for(j = 1; j <= i; j++){
			power *= number;
			printf("%d ", power);
		}
		printf("\n");
	}
	return 0;
}
```

## Question 5

| Output                                            | Similarly                                          |
| :------------------------------------------------ | -------------------------------------------------- |
| A B C D E<br />B C D E<br />C D E<br />D E<br />E | 1 2 3 4 5<br />2 3 4 5<br />3 4 5 <br />4 5<br />5 |
| A B C<br />B C<br />C                             | 1 2 3 <br />2 3 <br />3                            |

| Row  | Output    |
| :--- | --------- |
| 1    | 1 2 3 4 5 |
| 2    | 2 3 4 5   |
| 3    | 3 4 5     |
| 4    | 4 5       |
| 5    | 5         |

So, we iterate rows with a loop variable **i** from 1 to 5. At each row, we iterate from row number to 5 *(from i to 5)*. 

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int number, i, j;
	scanf("%d", &number);
	for(i = 0; i < number; i++){
		for(j = i; j < number; j++){
			printf("%c", 'A'+j);
		}
		printf("\n");
	}
	return 0;
}
```

## Question 6

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int number;
	scanf("%d", &number);
	int i, j;
	for(i = 1; i <= number; i++){
		for(j=1; j<=i; j++){
			printf("*");
		}
		for(j=i; j < number; j++){
			printf(" ");
		}
		printf("\n");
	}

	return 0;
}
```





 