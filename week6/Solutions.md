# Question 1

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

## Alternative

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

# Question 2

```c

#include <stdio.h>

int main() {
	int n, i, prev = 0, curr = 1, next;

	scanf("%d", &n);

	for(i=3; i <= n; i++){
		next = prev + curr;
		prev = curr;
		curr = next;
	}
    
	if(n <= 0){
		printf("Invalid!");
	}
	else if(n == 1){
		printf("%d", prev);
	}else{
		printf("%d", curr);
	}

	return 0;
}

```

# Question 3

```c
#include <stdio.h>

int main() {
	int n, m, i, j;

	scanf("%d %d", &n, &m);
	for(i=1; i<=n; i++){
		for(j=1; j <= m; j++){
			if(i == 1 || i == n || j == 1 || j == m){
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

# Question 4

```c
#include <stdio.h>

int main() {
	int n, i, j;

	scanf("%d", &n);

	for(i=1; i <= n; i++){
		for(j=1; j <= i-1; j++){
			printf(" ");
		}
		for(j=1; j <= i; j++){
			printf("*");
		}
		printf("\n");
	}
	return 0;
}
```

# Question 5

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

