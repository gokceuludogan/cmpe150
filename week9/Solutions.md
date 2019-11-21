# Solutions

## Question 1

```c
#include <stdio.h>
#include <stdlib.h>

void divide_with_remainder(int number, int divisor, int *res, int *rem){
	*res = number / divisor;
	*rem = number % divisor;
}
int main(void) {
	int number, divisor, result, remainder;

	scanf("%d %d", &number, &divisor);

	divide_with_remainder(number, divisor, &result, &remainder);

	printf("%d %d", result, remainder);

	return EXIT_SUCCESS;
}
```

### Alternative

This solution works too. However, the results are written over the user input. 

```c
#include <stdio.h>
#include <stdlib.h>

void divide_with_remainder(int number, int divisor, int *res, int *rem){
	*res = number / divisor;
	*rem = number % divisor;
}
int main(void) {
	int result, remainder;

	scanf("%d %d", &result, &remainder);

	divide_with_remainder(result, remainder, &result, &remainder);

	printf("%d %d", result, remainder);

	return EXIT_SUCCESS;
}
```

## Question 2

```c
#include <stdio.h>
#include <stdlib.h>

void swap(int *n1, int *n2){
	int temp;
	temp = *n2;
	*n2 = *n1;
	*n1 = temp;
}

int main(void) {
	int a, b;
	scanf("%d %d", &a, &b);
	swap(&a, &b);
	printf("%d %d", a, b);
	return EXIT_SUCCESS;
}
```

## Question 3

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {
	int i, numbers[8], sum = 0;

	for(i = 0; i < 8; i++){
		scanf("%d", &numbers[i]);
		sum += numbers[i];
	}

	float avg = sum / 8.0;

	for(i = 0; i < 8; i++){
		if(numbers[i] > avg){
			printf("%d\n", numbers[i]);
		}
	}

	return EXIT_SUCCESS;
}

```

## Question 4

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {

    int N, i;
	scanf("%d", &N);
	int numbers[N];
	for(i = 0; i < N; i++){
		scanf("%d", &numbers[i]);
	}

	int reverse[N];
	for(i = N-1; i >= 0; i--){
		reverse[N-1-i] = numbers[i];
	}

	for(i = 0; i < N; i++){
		printf("%d", reverse[i]);
	}

	return EXIT_SUCCESS;
}
```

