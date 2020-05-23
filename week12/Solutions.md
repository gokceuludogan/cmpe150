# Question 1

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

int main() {
	int size;
	scanf("%d", &size);
	int numbers[size];
	read_array(numbers, size);
	if(is_symmetric(numbers, size)){
		printf("Symmetric");
	}else{
		printf("Not symmetric");
	}
	return 0;
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

# Question 2

## a

```c
#include <stdio.h>
#include <stdlib.h>

void read_array(int arr[], int size){
	int i;
	for(i = 0; i < size; i++){
		scanf("%d", &arr[i]);
	}
}

int main() {
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
	return 0;
}

```

### b

```c
#include <stdio.h>
#include <stdlib.h>

void read_array(int arr[], int size){
	int i;
	for(i = 0; i < size; i++){
		scanf("%d", &arr[i]);
	}
}
int main() {
	int size;
	scanf("%d", &size);
	int numbers[size];
	read_array(numbers, size);
	int prev_el = numbers[0];
	int i, counter = 1, max_counter = 1, max_el = numbers[0];
	for(i=1; i<size; i++){
		if(numbers[i] == prev_el){
			counter++;
		}else{
            if(counter > max_counter){
				max_counter = counter;
				max_el = prev_el;
			}
			printf("%d %d\n", counter, prev_el);
			prev_el = numbers[i];
			counter = 1;
		}
	}
	printf("%d %d\n", counter, prev_el);
	printf("Max: %d %d", max_counter, max_el);
	return 0;
}
```

# Question 3 

```c
#include <stdio.h>

int main(){
	int x[10] = {1,2,3,4,5};
	int i;

	for(i = 0; i < 5; i++){
		printf("%d %p ",*(x+i), (x+i));	
	}
	return 0;
}
```

# Question 4

```c
#include <stdio.h>

void rightShiftA(int N, int arr[N], int T){
	int i;
	int temp_arr[N];

	T %= N;
	for(i = 0 ; i < N ; i++)
		temp_arr[(i+T)%N] = arr[i];

	for(i = 0 ; i < N ; i++)
		arr[i] = temp_arr[i];
}


int main()
{
	int i;

	int N;
	scanf("%d", &N);

	int arr[N];
	for(i = 0 ; i < N ; i++)
		scanf("%d", &arr[i]);

	int T;
	scanf("%d", &T);

	rightShiftA(N, arr, T);

	for(i = 0 ; i < N ; i++)
		printf("%d ", arr[i]);

    return 0;
}
```

# Question 5

```c
#include <stdio.h>

int main() {
	int R=4, C=4;
	int i, j, k, l;
	char arr[6][6] = {{0}}; // initialize the matrix with 0's

	for(i = 1 ; i <= R ; i++){
		scanf("%s", arr[i]+1); // read the input line by line and put it inside 0's
	}

	/*for(i = 0 ; i <= R+1 ; i++){
		for(j = 0 ; j <= C+1 ; j++){
			printf("%c", arr[i][j]); // or print with %d
		}
		printf("\n");
	}*/
	char max_char = '*';
	int max_counter = 0;
	for(i = 1; i <= R; i++){
		for(j = 1; j <= C; j++){
			if(arr[i][j] >= 'a' && arr[i][j] <= 'z'){
				int current_counter = 0;
				for(k = -1 ; k <= 1 ; k++){
					for(l = -1 ; l <= 1 ; l++){
						if(arr[i+k][j+l] == '*'){
							current_counter++;
						}
					}
				}
				if(current_counter == max_counter && arr[i][j] < max_char){
					max_char= arr[i][j];
					max_counter = current_counter;
				}
				if(current_counter > max_counter){
					max_char = arr[i][j];
					max_counter = current_counter;
				}
			}
		}
	}

	printf("%c %d", max_char, max_counter);

	return 0;
}
```

# Question 6

```c
#include <stdio.h>
#include <string.h>

void normalizeString(char s[]){
    if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
        s[strlen(s)-2] = '\0';
    else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
        s[strlen(s)-1] = '\0';
}

int main(){
    int n;
    char sentence[1001], word[21];
    fgets(sentence, 1000, stdin);
    scanf("%d %s", &n, word);

    normalizeString(sentence);
    normalizeString(word);

    int i, num_of_space = 1;
    for(i = 0; num_of_space < n && i < strlen(sentence); i++){
        if(sentence[i] == ' ')
            num_of_space++;
    }

    // last word
    if(num_of_space < n){
        sentence[strlen(sentence)] = ' ';
        sentence[strlen(sentence)+1] = '\0';
        strcat(sentence, word);
    }else{
        char temp[1000] = "";
        strcpy(temp, sentence+i);
        strcpy(sentence+i, word);
        sentence[i+strlen(word)] = ' ';
        strcpy(sentence+i+strlen(word)+1, temp);
    }

    printf("%s", sentence);

    return 0;
}
```

## Alternative

```c
/*
 ============================================================================
 Name        : week12_q6.c
 Author      : 
 Version     :
 Copyright   : Your copyright notice
 Description : Hello World in C, Ansi-style
 ============================================================================
 */

#include <stdio.h>
#include <string.h>

void normalizeString(char s[]){
	if(s[strlen(s)-2] == '\r' || s[strlen(s)-2] == '\n')
		s[strlen(s)-2] = '\0';
	else if(s[strlen(s)-1] == '\r' || s[strlen(s)-1] == '\n')
		s[strlen(s)-1] = '\0';
}

int main(){
	int n;
	char sentence[1001], word[21];
	fgets(sentence, 1000, stdin);
	scanf("%d %s", &n, word);

	//normalizeString(sentence);
	sentence[strlen(sentence)-2] = '\0';
	normalizeString(word);

	int i, num_of_space = 1;
	for(i = 0; num_of_space < n && i < strlen(sentence); i++){
		if(sentence[i] == ' ')
			num_of_space++;
	}

	//printf("%d", i);
	// last word
	if(num_of_space < n){
		sentence[strlen(sentence)] = ' ';
		sentence[strlen(sentence)+1] = '\0';
		strcat(sentence, word);
	}else{
		char temp[1000] = "";
		strcpy(temp, sentence+i);
		strcpy(sentence+i, word);
		sentence[strlen(sentence)+1] = '\0';
		sentence[strlen(sentence)] = ' ';
		strcat(sentence, temp);
	}
	printf("%s", sentence);
	return 0;
}
```

# Question 7

```c
#include <stdio.h>

int main() {
   char line[151];
   fgets(line, 150, stdin);
   int i, j;

   for(i = 0; line[i] != '\0'; i++){
	  char ch = line[i];
	  if(!(ch >= 'a' && ch <= 'z') && !(ch >= 'A' && ch <= 'Z')){
		  for(j = i; line[j] != '\0'; j++){
			  line[j] = line[j + 1];
		  }
		  i--;
	  }
   }

   printf("%s\n", line);
   return 0;
}

```

