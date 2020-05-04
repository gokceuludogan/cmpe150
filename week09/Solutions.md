# Solutions

## Question 1

### a.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N;
	scanf("%d", &N);
	int arr[N];
	int i, sum = 0;
	for(i = 0; i < N; i++){
		scanf("%d", &arr[i]);
		sum += arr[i];
	}
	printf("%d %f", sum, 1.0 * sum / N);
	return 0;
}
```

### b.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N;
	scanf("%d", &N);
	int arr[N];
	int i, sum = 0;
	for(i = 0; i < N; i++){
		scanf("%d", &arr[i]);
		sum += arr[i];
	}
	sum /= N;
	for(i = 0; i < N; i++){
		if(arr[i] > sum){
			printf("%d ", arr[i]);
		}
	}
	return 0;
}
```

## Question 2

```c
#include <stdio.h>
#include <stdlib.h>

int main(){
	char sentence[50];
	int size = 0, i;
	while(1){
		char read;
		scanf("%c", &read);
		if(read == '\n'){
			break;
		}else{
			sentence[size] = read;
			size++;
		}
	}
	char encrypted[size];
	for(i = 0; i < size; i++){
		encrypted[i] = sentence[i] + 1;
		printf("%c", encrypted[i]);
	}
	printf("\n");
	for(i = 0; i < size; i++){
		printf("%c", encrypted[i] - 1);
	}
	printf("\n");
	return 0;
}

```

## Question 3

### a.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N;
	scanf("%d", &N);
	int arr[N], i;
	for(i = 0; i < N; i++){
		scanf("%d", &arr[i]);
	}
	for(i = N - 1; i >= 0; i--){
		printf("%d ", arr[i]);
	}
	return 0;
}
```

### b.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N;
	scanf("%d", &N);
	int arr[N], i;
	for(i = 0; i < N; i++){
		scanf("%d", &arr[i]);
	}
	for(i = 0; i <= N/2; i++){
		int temp = arr[i];
		arr[i] = arr[N-1-i];
		arr[N-1-i] = temp;
	}
	for(i = 0; i < N; i++){
		printf("%d ", arr[i]);
	}

	return 0;
}
```

## Question 4

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N, M;
	scanf("%d%d", &N, &M);
	int first_arr[N], second_arr[M], i, j;
	for(i = 0; i < N; i++){
		scanf("%d", &first_arr[i]);
	}
	for(i = 0; i < M; i++){
		scanf("%d", &second_arr[i]);
	}
	int start_index = -1;
	for(j = 0; j < M - N; j++){
		int is_included = 1;
		for(i = 0; i < N; i++){
			if(first_arr[i] != second_arr[j+i]){
				is_included = 0;
				break;
			}
		}
		if(is_included){
			start_index = j;
		}
	}
	if(start_index != -1){
		printf("%d", start_index);
	}
	return 0;
}
```

### Alternative

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N, M;
	scanf("%d%d", &N, &M);
	int first_arr[N], second_arr[M], i, j;
	for(i = 0; i < N; i++){
		scanf("%d", &first_arr[i]);
	}
	for(i = 0; i < M; i++){
		scanf("%d", &second_arr[i]);
	}

    for(j = 0; j < M - N; j++){
		for(i = 0; i < N; i++){
			if(first_arr[i] != second_arr[j+i]){
				break;
			}
		}
		if(i == n){
			printf("%d", i);
		}
	}

	return 0;
}
```



## Question 5

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N;
	scanf("%d", &N);
	int numbers[N], i;
	int counts[101] = {0};
	for(i = 0; i < N; i++){
		scanf("%d", &numbers[i]);
		counts[numbers[i]]++;
	}
	for(i = 0; i < 101; i++){
		if(counts[i]){
			printf("%d: %d\n", i, counts[i]);
		}
	}

	return 0;
}
```

## Question 6

### a.

```c
#include <stdio.h>
#include <stdlib.h>
int main() {
	int N, M;
	scanf("%d%d", &N, &M);
	int i, j;
	int first_arr[N];
	int second_arr[M];
	for(i=0; i<N; i++){
		scanf("%d", &first_arr[i]);
	}
	for(j=0; j<M; j++){
		scanf("%d", &second_arr[j]);
	}

	for(i=0; i<N; i++){
		for(j=0; j<M; j++){
			if(first_arr[i] == second_arr[j]){
				printf("%d %d \n", first_arr[i], i);
			}
		}
	}
	return 0;
}

```

### b.

```c
#include <stdio.h>
#include <stdlib.h>
int main() {
	int N, M;
	scanf("%d%d", &N, &M);
	int i, j;
	int first_arr[N];
	int second_arr[M];
	for(i=0; i<N; i++){
		scanf("%d", &first_arr[i]);
	}
	for(j=0; j<M; j++){
		scanf("%d", &second_arr[j]);
	}

	for(i=0; i<N; i++){
		for(j=0; j<M; j++){
			if(first_arr[i] == second_arr[j]){
				printf("%d %d \n", first_arr[i], i);
				break;
			}
		}
	}
	return 0;
}
```

## Question 7

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int N, i, j;
	scanf("%d", &N);
	int sequence[N];
	for(i=0; i<N; i++){
		scanf("%d", &sequence[i]);
	}
	for(i=0; i<N; i++){
		if(sequence[i] == 3){
			for(j=0; j<N; j++){
				if(sequence[j] == 4 && sequence[j-1] != 3){
					int temp = sequence[i+1];
					sequence[i+1] = sequence[j];
					sequence[j] = temp;
				}
			}
		}
	}
	for(i=0; i<N; i++){
		printf("%d ", sequence[i]);
	}
	return 0;
}
```



