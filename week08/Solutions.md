# Solutions

## Question 1

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	char a = 'F';
	int b = 6;
	float c = 3.5;
	char *ptr_a = &a;
	int *ptr_b = &b;
	float *ptr_c = &c;

	printf("The address of char\t%p\n", &a);
	printf("The address of int\t%p\n", &b);
	printf("The address of float\t%p\n", &c);
	printf("The address of char*\t%p\n", &ptr_a);
	printf("The address of int*\t%p\n", &ptr_b);
	printf("The address of float*\t%p\n", &ptr_c);

	printf("The value of char\t%c\n", a);
	printf("The value of int\t%d\n", b);
	printf("The value of float\t%f\n", c);
	printf("The value of char*\t%p\n", ptr_a);
	printf("The value of int*\t%p\n", ptr_b);
	printf("The value of float*\t%p\n", ptr_c);
    
    printf("The value addressed by char* %c", *ptr_a);
    printf("The value addressed by int* %d", *ptr_b);
    printf("The value addressed by float* %d", *ptr_c);
    
	printf("The size of char\t%lu\n", sizeof(a));
	printf("The size of int  \t%lu\n", sizeof(b));
	printf("The size of float\t%lu\n", sizeof(c));
	printf("The size of char*\t%lu\n", sizeof(ptr_a));
	printf("The size of int*\t%lu\n", sizeof(ptr_b));
	printf("The size of float*\t%lu\n", sizeof(ptr_c));
	return 0;
}

```

## Question 2

```c
#include <stdio.h>
#include <stdlib.h>

void increment(int a){
	printf("Address: %p\n", &a);
	a++;
}
void decrement(int *ptr){
	printf("Address: %p\n", &(*ptr));
	(*ptr)++;
}
int main() {
	int number;
	scanf("%d", &number);
	printf("Before %p\n", &number);
	increment(number);
	printf("%d\n", number);
	decrement(&number);
	printf("%d\n", number);
	return 0;
}

```

## Question 3

```c
#include <stdio.h>
#include <stdlib.h>

void divide_with_remainder(int number, int divisor, int *res, int *rem){
	*res = number / divisor;
	*rem = number % divisor;
}
int main() {
	int number, divisor, result, remainder;

	scanf("%d %d", &number, &divisor);

	divide_with_remainder(number, divisor, &result, &remainder);

	printf("%d %d", result, remainder);

	return 0;
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
int main() {
	int result, remainder;

	scanf("%d %d", &result, &remainder);

	divide_with_remainder(result, remainder, &result, &remainder);

	printf("%d %d", result, remainder);

	return 0;
}
```

## Question 4

```c
#include <stdio.h>
#include <stdlib.h>

void swap(int *n1, int *n2){
	int temp;
	temp = *n2;
	*n2 = *n1;
	*n1 = temp;
}

int main() {
	int a, b;
	scanf("%d %d", &a, &b);
	swap(&a, &b);
	printf("%d %d", a, b);
	return 0;
}
```

## Question 5

```c
#include <stdio.h>
#include <stdlib.h>

int local_max(int n, int *ptr_to_greatest) {
    int i, previous, current, next;
    int num_of_local_max = 0;
    scanf("%d", &current);
    scanf("%d", &next);
    for (i = 1; i < n - 1; i ++) {
    	previous = current;
    	current = next;
    	scanf("%d", &next);
    	if (current > previous && current > next) {
    		num_of_local_max += 1;
    		if(num_of_local_max == 1 || current > *ptr_to_greatest){
    			*ptr_to_greatest = current;
    		}
    	}
    }
    return num_of_local_max;
}

int main() {
    int n, num_of_local_max = 0, greatest;
    scanf("%d", &n);
    num_of_local_max = local_max(n, &greatest);
    printf("Number of local max: %d Greatest local max: %d", num_of_local_max, greatest);
    return 0;
}
```

