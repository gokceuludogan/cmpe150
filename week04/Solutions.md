# Warm up

```c
#include <stdio.h>

int main() {
	char a, b;
	int result;
	scanf("%c%c", &a, &b);

	// printf("%c", a);
	// printf("%c", 'a');
	// printf("a");
	// printf("%d\n", a);
	// printf("%d\n", '0');
	// printf("%d\n", a - '0');
	// printf("%d\n", a - 0);
	// printf("%d\n", 'a' - '0');
	result = (a - '0') * (b - '0');
	printf("%d", result);
	return 0;
}

```

## Alternative

```c
#include <stdio.h>
int main() {
	char first_digit, second_digit; // keeps the digits as characters.
	scanf("%c %c", &first_digit, &second_digit);
	// we subtract '0' character from the input since digits are successive in ASCII table.
	// '0' => 48
	// '1' => 49, etc.

	int first_number = first_digit - '0'; // finds the integer value of first digit.
	int second_number = second_digit - '0'; // finds the integer value of second digit.

	printf("%d", first_number * second_number);
	return 0;
}
```

# Question 1

```c
#include <stdio.h>
#include "teachingcodes.h"
int main() {
	int year;
	scanf("%d", &year);

	if(year % 4 == 0){
		printf("%d is a leap year.", year);
	}else{
		printf("%d is not a leap year.", year);
	}

	return 0;
}
```

## Alternative

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int year;
	scanf("%d", &year);
	printf("%d", year % 4);
	if(year % 4){
		printf("not a leap year");
	}else{
		printf("leap year");
	}
	return 0;
}
```



# Question 2

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Ignore the cases where the point is on an axis. 
    int x, y;
	scanf("%d %d", &x, &y);
    
    if(x > 0 && y > 0){
		printf("First quadrant");
	}else if(x < 0 && y > 0){
		printf("Second quadrant");
	}else if(x < 0 && y < 0){
		printf("Third quadrant");
	}else if(x > 0 && y < 0){
		printf("Fourth quadrant");
	}
```

## Alternative solution

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	// Ignore the cases where the point is on an axis. 

	int x, y;
	scanf("%d %d", &x, &y);

	if(x > 0){
		if(y > 0){
			printf("First quadrant");
		}else{
			printf("Fourth quadrant");
		}
	}else{
		if(y > 0){
			printf("Second quadrant");
		}else{
			printf("Third quadrant");
		}
	}
```

# Question 3

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	char op;
	int num1, num2;

	scanf("%d %d %c", &num1, &num2, &op);

	if(op == '+'){
		printf("%d", num1 + num2);
	}else if (op == '-'){
		printf("%d", num1 - num2);
	}else if (op == '*'){
		printf("%d", num1 * num2);
	}else if (op == '/'){
		printf("%d", num1 / num2);
	}else{
		printf("Invalid operation!");
	}

	return 0;
}

```

# Question 4

## Solution using Nested Ifs

```c
#include <stdio.h>
int main() {

	int num1, num2, num3, largest;
	scanf("%d %d %d", &num1, &num2, &num3);

	if(num1 >= num2){
		if(num3 > num1){
			largest = num3;
		}else{
			largest = num1;
		}
	}else{
		if(num3 > num2){
			largest = num3;
		}else{
			largest = num2;
		}
	}

	printf("%d", largest);
	return 0;
}
```

## Solution without Nested Ifs

```c
#include <stdio.h>

int main() {

	int num1, num2, num3, largest;
	scanf("%d %d %d", &num1, &num2, &num3);

	if(num1 >= num2){
		largest = num1;
	}else{
		largest = num2;
	}

	if(num3 > largest){
		largest = num3;
	}

	printf("%d", largest);
	return 0;
}

```

## Solution without Nested Ifs - 2

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int num1, num2, num3;
	scanf("%d%d%d", &num1, &num2, &num3);
	if(num1 > num2 && num1 > num3){
		printf("%d", num1);
	}else if(num2 > num1 && num2 > num3){
		printf("%d", num2);
	}else{
		printf("%d", num3);
	}

	return 0;
}
```



## Solution with ternary if else

```c
#include <stdio.h>

int main() {

	int num1, num2, num3, largest;
	scanf("%d %d %d", &num1, &num2, &num3);

	largest = num1 > num2 ? num1 : num2;
	largest = num3 > largest ? num3 : largest;

	printf("%d", largest);
	return 0;
}
```

# Question 5

```c
#include <stdio.h>
int main() {
	int day_number;
	scanf("%d", &day_number);

	switch(day_number){
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

