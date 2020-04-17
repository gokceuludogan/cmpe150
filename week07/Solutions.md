# Solutions

## Question 1

```c
#include <stdio.h>
#include <stdlib.h>

char to_upper(char lowercase){
	if(lowercase >= 'a' && lowercase <= 'z'){
        	lowercase = lowercase - 'a' + 'A';
    	}
	return lowercase;
}

int main() {
	char input, output;
	scanf("%c", &input);
	while(input != '\n'){
		output = to_upper(input);
		printf("%c", output);
		scanf("%c", &input);
	}
	return 0;
}

```

### Alternative Solution

```c
#include <stdio.h>
#include <stdlib.h>

char to_upper(char lowercase){
	if(lowercase >= 'a' && lowercase <= 'z'){
        	lowercase = lowercase - 'a' + 'A';
    	}
	return lowercase;
}

int main() {
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
	return 0;
}

```

## Question 2

```c
#include <stdio.h>
#include <stdlib.h>

int find_max(int a, int b, int c){
	int max;
	max = a > b ? a : b;
	max = max > c ? max : c;
	return max;
}
int main() {
	printf("%d\n", find_max(5, 3, 8));
	printf("%d", find_max(14, -1, 9));
	return 0;
}
```

## Question 3

```c

#include <stdio.h>
#include <stdlib.h>

int factorial(int n){
	int i, fact = 1;
	for(i=2; i<=n; i++){
		fact = fact * i;
	}
	return fact;
}

int permutation(int n, int k){
	return factorial(n) / factorial(n-k);
}

int combinatorial(int n, int k){
	return factorial(n) / (factorial(n-k) * factorial(k));
}

int selection(char choice, int n, int k){
	if(choice == 'C'){
		return combinatorial(n, k);
	}else if(choice == 'P'){
		return permutation(n, k);
	}else{
		return -1;
	}
}
int main(void) {
	printf("%d\n", factorial(5));
	printf("%d\n", permutation(5, 2));
	printf("%d\n", combinatorial(5, 2));
	printf("%d\n", selection('C', 5, 2));
	printf("%d\n", selection('P', 5, 2));
	printf("%d\n", selection('X', 5, 2));

	return EXIT_SUCCESS;
}

```

## Question 4

```c
#include <stdio.h>
#include <stdlib.h>

int fetchDigit(int number, int n){
	int counter = 0;
	while(number > 0){
		int digit = number % 10;
		number /= 10;
		counter++;
		if(counter == n){
			return digit;
		}
	}
	return -1;

}
int main() {
	int z, x;
	scanf("%d%d", &z, &x);
	int result = fetchDigit(z, x);
	if(result != -1){
		printf("%d", result);
	}else{
		printf("Incorrect input");
	}
	return 0;
}
```

### Alternative

```c
#include <stdio.h>
#include <stdlib.h>

int fetchDigit(int number, int n){
	int ctr = 0;
	int last_digit = -1;
	while(number > 0){
		int digit = number % 10;
		number = number / 10;
		ctr++;
		if(n == ctr){
			last_digit = digit;
			break;
		}
	}
	return last_digit;
}

int main() {
	int z, x;
	scanf("%d%d", &z, &x);
	int result = fetchDigit(z, x);
	if(result == -1){
		printf("Incorrect input");
	}else{
		printf("%d", result);
	}
	return 0;
}
```

## Question 5

```c
#include <stdio.h>
#include <stdlib.h>

void pyramid(int num_of_rows){
	int i, j, t=1;
	for(i=1;i<=num_of_rows;i++){
		for(j=i; j<num_of_rows; j++){
			printf(" ");
		}
		for(j=1; j<=i; j++)
			printf("%d ", t++);
		printf("\n");
	}
}

int main() {
	int rows;
	scanf("%d", &rows);
	pyramid(rows);
	return 0;
}
```

### Alternative

```c
#include <stdio.h>
#include <stdlib.h>

void pyramid(int num_of_rows){
	int i, j, temp = 1;
	for(i=1; i<=num_of_rows; i++){
		for(j=1;  j <= num_of_rows - i; j++){
			printf(" ");
		}
		for(j=1; j<=i; j++){
			printf("%d ", temp);
			temp++;
		}
		printf("\n");
	}
}
int main() {
	pyramid(3);
	return 0;
}

```

## Question 6

```c
#include <stdio.h>
#include <stdlib.h>

int is_perfect(int number){
	int i, sum=0;
	for(i=1; i<number; i++){
		if(number % i == 0){
			sum += i;
			printf("%d ", i);
		}
	}
	return sum == number;
}

int main() {
	int input;
	scanf("%d", &input);
	printf("\n%d", is_perfect(input));
	return 0;
}

```

## Question 7

```c
#include <stdio.h>
#include <stdlib.h>
#include "teachingcodes.h"

int reverse(int number){
	int reversed = 0;
	while(number > 0){
		reversed = number % 10 + reversed * 10;
		number /= 10;
	}
	return reversed;

}

int main() {
	int input;
	scanf("%d", &input);
	printf("%d", reverse(input));
	return 0;
}
```

### Alternative

```c
#include <stdio.h>
#include <stdlib.h>

int reverse(int num){
	int rev_num = 0;
	while(1){
		int digit = num % 10;
		rev_num = rev_num * 10 + digit;
		num /= 10;
        if(num == 0){
            break;
        }
	}
	return rev_num;
}
int main() {
	printf("%d", reverse(1234));
	return 0;
}

```

## Question 8

```c
#include <stdio.h>
#include <stdlib.h>

int to_binary(int number){
	int bin = 0, i = 1;
	while(number > 0){
		bin += (number % 2) * i;
		i *= 10;
		number /= 2;
		printf("%d %d %d\n", bin, i, number);
	}
	return bin;
}

int main() {
	int input;
	scanf("%d", &input);
	printf("%d", to_binary(input));
	return 0;
}

```

## Question 9

```c
#include <stdio.h>
#include <stdlib.h>

int fibonacci_number(int number){
	int i, prev = 0, curr = 1, next;

	for (i = 2; i < number; ++i) {
		next = prev + curr;
		prev = curr;
		curr = next;
	}

	if(number == 1){
		return prev;
	}else{
		return curr;
	}
}

int main() {
	int input;
	scanf("%d", &input);
	printf("%d", fibonacci_number(input));
	return 0;
}

```

