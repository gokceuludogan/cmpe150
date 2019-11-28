# Solutions

## Question 1

```c
#include <stdio.h>
#include <stdlib.h>

void print_array(int arr[], int N){
	int i;
	for(i = 0; i < N; i++){
		printf("%d", arr[i]);
	}
}

void read_array(int arr[], int N){
	int i;
	for(i = 0; i < N; i++){
		scanf("%d", &arr[i]);
	}
}

int main(void) {
	int size;
	scanf("%d", &size);
	int numbers[size];
	read_array(numbers, size);
	print_array(numbers, size);
	return EXIT_SUCCESS;
}
```

## Question 2

```c
#include <stdio.h>
#include <stdlib.h>
void read_array(int arr[], int N){
	int i;
	for(i = 0; i < N; i++){
		scanf("%d", &arr[i]);
	}
}

int is_symmetric(int arr[], int N){
	int i;
	for(i = 0; i < N/2; i++){
		if(arr[i] != arr[N-i-1]){
			return 0;
		}
	}
	return 1;
}

int main(void) {
	int size;
	scanf("%d", &size);
	int numbers[size];
	read_array(numbers, size);
	if(is_symmetric(numbers, size)){
		printf("Symmetric");
	}else{
		printf("Not symmetric");
	}
	return EXIT_SUCCESS;
}
```

## Alternative

```c
int is_symmetric(int arr[], int N){
	int i;
	for(i = 0; i < N/2; i++){
		if(arr[i] == arr[N-i-1]){
			continue;
		}else{
            return 0;
        }
	}
	return 1;
}
```

## Question 3

```c
#include <stdio.h>
#include <stdlib.h>
void read_array(int arr[], int N){
	int i;
	for(i = 0; i < N; i++){
		scanf("%d", &arr[i]);
	}
}

void find_common(int arr[], int size1, int arr2[], int size2){
	int i, j;
	for(i = 0; i < size1; i++){
		for(j = 0; j < size2; j++){
			if(arr[i] == arr2[j]){
				printf("%d %d\n", arr[i], i);
			}
		}
	}
}

int main(void) {
	int size1, size2;

	scanf("%d %d", &size1, &size2);

	int num[size1], num2[size2];
	read_array(num, size1);
	read_array(num2, size2);
	find_common(num, size1, num2, size2);
	return EXIT_SUCCESS;
}
```

### Homework

If the element from the first array is equal to an element from second array, then we should not continue iterating the second array for this element. So, we use a **break**. Then the program continues to check the second array for the next element of the first array.   

```c
#include <stdio.h>
#include <stdlib.h>
void read_array(int arr[], int N){
	int i;
	for(i = 0; i < N; i++){
		scanf("%d", &arr[i]);
	}
}

void find_common(int arr[], int size1, int arr2[], int size2){
	int i, j;
	for(i = 0; i < size1; i++){
		for(j = 0; j < size2; j++){
			if(arr[i] == arr2[j]){
				printf("%d %d\n", arr[i], i);
                break;
			}
		}
	}
}

int main(void) {
	int size1, size2;

	scanf("%d %d", &size1, &size2);
	int num[size1], num2[size2];
	read_array(num, size1);
	read_array(num2, size2);
	find_common(num, size1, num2, size2);
	return EXIT_SUCCESS;
}
```

## Question 4

**a.**

```c
/*
 ============================================================================
 Name        : w10_consecutive.c
 Author      : 
 Version     :
 Copyright   : Your copyright notice
 Description : Hello World in C, Ansi-style
 ============================================================================
 */

#include <stdio.h>
#include <stdlib.h>

void read_array(int arr[], int size){
	int i;
	for(i = 0; i < size; i++){
		scanf("%d", &arr[i]);
	}
}

int main(void) {
	int size;
	scanf("%d", &size);
	int numbers[size];
	read_array(numbers, size);
	int prev_el = numbers[0];
	int i, counter = 1;
	for(i=1; i<size; i++){
		if(numbers[i] == prev_el){
			counter++;
		}else{
			printf("%d %d\n", counter, prev_el);
			prev_el = numbers[i];
			counter = 1;
		}
	}
	printf("%d %d\n", counter, prev_el); // To print the last element since it is not compared with any value.
	return EXIT_SUCCESS;
}

```

**b.**

```c
#include <stdio.h>
#include <stdlib.h>

void read_array(int arr[], int size){
	int i;
	for(i = 0; i < size; i++){
		scanf("%d", &arr[i]);
	}
}
int main(void) {
	int size;
	scanf("%d", &size);
	int numbers[size];
	read_array(numbers, size);
	int prev_el = numbers[0];
	int i, counter = 1, max_counter = 1, max_el = numbers[0];
	for(i=1; i<size; i++){
		if(numbers[i] == prev_el){
			counter++;
			if(counter > max_counter){
				max_counter = counter;
				max_el = prev_el;
			}
		}else{
			printf("%d %d\n", counter, prev_el);
			prev_el = numbers[i];
			counter = 1;
		}
	}
	printf("%d %d\n", counter, prev_el);
	printf("Max: %d %d", max_counter, max_el);
	return EXIT_SUCCESS;
}

```

## Question 5

## Section 3

```c
#include <stdio.h>
#include <stdlib.h>
void read_array(int arr[], int N){
	int i;
	for(i = 0; i < N; i++){
		scanf("%d", &arr[i]);
	}
}

void delete_element(int arr[], int size, int index){
	int i;
	for(i=index; i < size-1; i++){
		arr[i] = arr[i+1];
	}
}

int main(void) {
	int size, i;
	scanf("%d", &size);
	int numbers[size];
	read_array(numbers, size);
	delete_element(numbers, size, 2);
	size = size - 1;
	for(i = 0; i < size; i++){
		printf("%d", numbers[i]);
	}
	return EXIT_SUCCESS;
}
```

## Section 2

```c
#include <stdio.h>
#include <stdlib.h>
void delete_element(int arr[], int *len, int index){
	int i;
	for(i=index; i<*len-1; i++){
		arr[i] = arr[i+1];
	}
	*len = *len - 1;
}

int main(void) {
	int size = 5;
	int i;
	int arr[5] = {1, 5, 6, 8, 9};
	delete_element(arr, &size, 2);
	printf("%d\n", size);
	for(i=0; i<size; i++){
		printf("%d\n", arr[i]);
	}
	return EXIT_SUCCESS;
}
```

## Homework

```c
#include <stdio.h>
#include <stdlib.h>

void read_array(int arr[], int size){
	int i;
	for(i = 0; i < size; i++){
		scanf("%d", &arr[i]);
	}
}
void print_array(int arr[], int size){
	int i;
	for(i = 0; i < size; i++){
		printf("%d ", arr[i]);
	}
}

void delete_element(int arr[], int *len, int index){
	int i;
	for(i=index; i<*len-1; i++){
		arr[i] = arr[i+1];
	}
	*len = *len - 1;
}

int main(void) {
	int size1, size2;
	scanf("%d %d", &size1, &size2);
	int first_array[size1], second_array[size2];
	read_array(first_array,size1);
	read_array(second_array, size2);
	int i, j;
	for(i=0 ; i<size1 ;i++){
		for(j=0 ; j<size2 ; j++){
			if(first_array[i] == second_array[j]){
				delete_element(first_array, &size1, i);
                i = i - 1; // since we have deleted an element, the next element is placed in that index. Let's say we have deleted element at second index. The element at the third index previously is in the second index now. So, we must check this index again, thus we decreased i by one. 
				break;
			}
		}
	}
	print_array(first_array, size1)

	return EXIT_SUCCESS;
}
```

