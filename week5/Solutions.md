# Solutions

#### Warm up: Finding largest of three numbers with ternary if

```c
#include <stdio.h>

int main() {

	int num1, num2, num3, result = 0;
	scanf("%d %d %d", &num1, &num2, &num3);

	result += num1 % 2 == 1 ? num1 : 0;
	result += num2 % 2 == 1 ? num2 : 0;
	result += num3 % 2 == 1 ? num3 : 0;

	printf("%d", result);
	return 0;
}
```



#### Question 1

```c
#include <stdio.h>
int main() {
	int day_number;
	scanf("%d", &day_number);

	switch(day_number % 7){
		case 1: printf("Monday");
		break;
		case 2: printf("Tuesday");
		break;
		case 3: printf("Wednesday");
		break;
		case 4: printf("Thursday");
		break;
		case 5: printf("Friday");
		break;
		case 6: printf("Saturday");
		break;
		case 7: printf("Sunday");
		break;
		default: printf("Not in range!");
	}
	return 0;
}
```



#### Question 2

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



#### Question 3

#### a.

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

#### b.

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

#### Question 4

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

#### Question 5

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