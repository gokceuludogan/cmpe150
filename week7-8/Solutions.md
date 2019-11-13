# Solutions

## Question 1

```c
#include <stdio.h>
#include <stdlib.h>

int find_max(int num1, int num2, int num3){
	int max;
	max = num1 > num2 ? num1 : num2;
	max = max > num3 ? max : num3;
	return max;
}

int main(void) {
	int result = find_max(5, 3, 8);
	printf("%d", result);
    printf("%d", find_max(14, -1, 9));
	return EXIT_SUCCESS;
}

```

## Question 2

```c
#include <stdio.h>
#include <stdlib.h>
#include "teachingcodes.h"

char to_upper(char lowercase){
	char uppercase;
	uppercase = lowercase - 'a' + 'A';
	return uppercase;
}

int main(void) {
	char input, output;
	scanf("%c", &input);
	while(input != '\n'){
		output = to_upper(input);
		printf("%c", output);
		scanf("%c", &input);
	}
	return EXIT_SUCCESS;
}

```

### Alternative Solution

```c
#include <stdio.h>
#include <stdlib.h>
#include "teachingcodes.h"

char to_upper(char lowercase){
	char uppercase;
	uppercase = lowercase - 'a' + 'A';
	return uppercase;
}

int main(void) {
	char input, output;
	scanf("%c", &input);
	while(1){
		output = to_upper(input);
		printf("%c", output);
		scanf("%c", &input);
		if(input == '\n'){
			break;
		}
	}
	return EXIT_SUCCESS;
}

```

## Question 3

```c
#include <stdio.h>
#include <stdlib.h>
int factorial(int num){
	int result=1, i;
	for(i=2; i<=num; i++){
		result *= i;
	}
	return result;
}

int sum_factorial_digit(int number){
	int sum = 0;
	while(number > 0){
		int last_digit = number % 10;
		sum += factorial(last_digit);
		number /= 10;
	}
	return sum;
}

int main(void) {
	int number;
	scanf("%d", &number);
	printf("%d", sum_factorial_digit(number));
	return EXIT_SUCCESS;
}

```

## Question 4

```c
#include <stdio.h>
#include <stdlib.h>
int is_prime(int num){
	int i;
	for(i=2; i<num; i++){
		if(num % i == 0){
			return 0;
		}
	}
	return 1;
}

int main(){
	int input, i;
	scanf("%d", &input);
	for(i=2; i<=input; i++){
		if(input % i == 0 && is_prime(i)){
			printf("%d ", i);
		}
	}
	return EXIT_SUCCESS;
}
```

## Question 5

```c
#include <stdio.h>
#include <stdlib.h>

void find_min_max(int num1, int num2, int num3, int *max_ptr, int *min_ptr){
	int max_value, min_value;
	max_value = num1 > num2 ? num1 : num2;
	max_value = max_value > num3 ? max_value : num3;

	min_value = num1 < num2 ? num1 : num2;
	min_value = min_value < num3 ? min_value : num3;

	*max_ptr = max_value;
	*min_ptr = min_value;
}

int main(void) {
	int max, min;
	find_min_max(5, 4, 3, &max, &min);
	printf("%d %d", max, min);
	return EXIT_SUCCESS;
}

```

