# Solutions

## Warm up

### If-else

```c
#include <stdio.h>

int main() {
	int first_num, second_num;
	scanf("%d %d", &first_num, &second_num);

	if(first_num > second_num ){
		printf("%d", first_num);
	}else{
        printf("%d", second_num);
    }
	return 0;
}

```

### Switch-case

```c
#include <stdio.h>

int main() {
	int first_num, second_num;
	scanf("%d %d", &first_num, &second_num);

	switch(first_num > second_num ){
		case 1: printf("%d", first_num);
		break;
		case 0: printf("%d", second_num);
		break;
	}
	return 0;
}

```

## Question 1

### a.

#### While

```c
#include <stdio.h>

int main() {
	int threshold, i = 1, result = 0;
	scanf("%d", &threshold);

	while(i <= threshold){
		result += i++;
	}
    
	printf("%d\n", result);
	return 0;
}

```

#### For

```c
#include <stdio.h>

int main() {
	int threshold, i, result = 0;
	scanf("%d", &threshold);

    for(i=1; i<= threshold; i++){
     	result += i;   
    }
    
	printf("%d\n", result);
	return 0;
}

```

### b.

#### While

```c
#include <stdio.h>

int main() {
	int threshold, i = 1, result = 0;

	scanf("%d", &threshold);

	while(i <= threshold){
        if(i % 2 == 1){
            result += i;
        }
		i++;
    }
    
	printf("%d\n", result);
	return 0;
}

```

#### For

```c
#include <stdio.h>

int main() {
	int threshold, i, result = 0;

	scanf("%d", &threshold);

    for(i=1; i<= threshold; i += 2){
        result += i;
    }
	
	printf("%d\n", result);
	return 0;
}

```

## Question 2

```c
#include <stdio.h>

int main() {
	int number, count = 0;
	scanf("%d", &number);

	while(number > 0){
		count += number % 2;
		number /= 10;
	}

	printf("%d", count);
	return 0;
}
```

Alternatively,

```c
#include <stdio.h>

int main() {
	int number, count = 0;
	scanf("%d", &number);

	while(number > 0){
        if(number % 2 == 1){
			count++;
        }
		number /= 10;
	}

	printf("%d", count);
	return 0;
}
```

## Question 3

```c
#include <stdio.h>

int main() {
	int number, max = 0;

	do{
		scanf("%d", &number);
		max = max > number ? max : number;
	}while(number > 0);

	printf("%d", max);
	return 0;
}
```

Alternatively,

```c
#include <stdio.h>

int main() {
	int number, max = 0;

	do{
		scanf("%d", &number);
		if(number > max){
			max = number;
		}
    }while(number > 0);

	printf("%d", max);
	return 0;
}

```

## Question 4

```c
#include <stdio.h>
int main() {
	char ch1, ch2;

	scanf("%c %c", &ch1, &ch2);
	
	for(; ch1 <= ch2; ch1++){
		printf("%c", ch1);
	}
    
	return 0;
}
```

Alternatively,

```c
#include <stdio.h>
int main() {
	char ch1, ch2, i;

	scanf("%c %c", &ch1, &ch2);

	i = ch1;
	while(i <= ch2){
		printf("%c ", i);
		i++;
	}
	return 0;
}
```

## Question 5

```c
#include <stdio.h>
int main() {
    int i, n, prev = 0, curr = 1, next;
    scanf("%d", &n);
	
    for (i = 2; i <= n; ++i) {
        next = prev + curr;
        prev = curr;
        curr = next;
    }
    
    if(n == 0){
        printf("%d", prev);
    }else{
        printf("%d", curr);
    }
    return 0;
}
```

## Question 6

## a.

```c
#include <stdio.h>

int main() {
	int number, i, is_prime = 0;

	scanf("%d", &number);

	for(i=2; i < number; i++){
		if(number % i == 0){
			is_prime = 1;
			break;
		}
	}
    
	if(is_prime != 0){
		printf("not prime");
	}else{
		printf("prime");
	}
	return 0;
}

```

## b.

```c
#include <stdio.h>

int main() {
	int number, i, j, is_prime;

	scanf("%d", &number);

	for(j=2; j<=number; j++){
		is_prime = 1;
		for(i=2; i < j; i++){
			if(j % i == 0){
				is_prime = 0;
			}
		}
		if(is_prime){
			printf("%d ", j);
		}
	}
	return 0;
}

```

