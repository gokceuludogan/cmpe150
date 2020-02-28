# Warm up

```c
#include <stdio.h>
int main() {
	int num;
	scanf("%d", &num);
	float result = (num / 3.0 + 10) * 2;
	printf("%.2f", result);
	return 0;
}
```

## Alternative

```c
#include <stdio.h>
int main() {
	int num;
	scanf("%d", &num);
	float result = ((float) num / 3 + 10) * 2;
	printf("%.2f", result);
	return 0;
}
```

# Q1

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int num1, num2, num3;
	scanf("%d%d%d", &num1, &num2, &num3);
	num1 = (num1 % 3 > 0) * num1;
	num2 = (num2 % 3 > 0) * num2;
	num3 = (num3 % 3 > 0) * num3;
	printf("%d", num1 + num2 + num3);
	return 0;
}

```

## Alternative 1

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int num1, num2, num3;
	scanf("%d%d%d", &num1, &num2, &num3);
	num1 = (num1 % 3 != 0) * num1;
	num2 = (num2 % 3 != 0) * num2;
	num3 = (num3 % 3 != 0) * num3;
	printf("%d", num1 + num2 + num3);
	return 0;
}

```

## Alternative 2

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int num1, num2, num3;
	scanf("%d%d%d", &num1, &num2, &num3);
	num1 = (num1 % 3 == 1 || num1 % 3 == 2) * num1;
	num2 = (num2 % 3 == 1 || num2 % 3 == 2) * num2;
	num3 = (num3 % 3 == 1 || num1 % 3 == 2) * num3;
	printf("%d", num1 + num2 + num3);
	return 0;
}

```

# Q2

```c
#include <stdio.h>
#include <stdlib.h>
int main(void) {
	char ch;
	scanf("%c", &ch);
	// printf("%d\n", ch - 'a'); // Finds the order of the lowercase letter
	// printf("%d\n", 'A'); // Prints the integer value of 'A'
	// printf("%d\n", ch - 'a' + 'A'); // Adds the order of the letter to integer value of A to find its uppercase version. Outputs the integer value of the uppercase.
	printf("%c\n", ch - 'a' + 'A');
	return 0;
}
```

## Alternative

``` c
#include <stdio.h>
int main() {
	char letter, uppercase;
	scanf("%c", &letter);
	int difference = 'a' - 'A'; 
	uppercase = letter - difference; 
	printf("%c", uppercase);
	return 0;
}
```

# Q3

```c
#include <stdio.h>
#define INCHES_IN_FOOT 12
#define CM_IN_INCH 2.54
int main() {
	int height;
	scanf("%d", &height);
	float height_in_feet = height / CM_IN_INCH / INCHES_IN_FOOT;
	printf("%f", height_in_feet);
	return 0;
}
```

# Q4

```c
#include <stdio.h>

int main() {
	char letter;
	scanf("%c", &letter);
	printf("%d", letter - '0' >= 0 && '9' - letter >= 0);
	return 0;
}
```

## Alternative

```c
#include <stdio.h>
#include <stdlib.h>
int main() {
	char ch;
	scanf("%c", &ch);
	int is_digit = ch >= '0' && ch <= '9';
	printf("%d", is_digit);
	return 0;
}
```

