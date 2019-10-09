# Warm up

```c
#include <stdio.h>
int main() {
	int num;
	scanf("%d", &num);
	float result;
	result = (num / 3.0 + 10) * 2;
	printf("%.2f", result);
	return 0;
}
```

# Q1

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

# Q2

```c
#include <stdio.h>
#define INCHES_IN_FOOT 12
#define CM_IN_INCH 2.54
int main() {
	int height;
	scanf("%d", &height);

	float height_in_feet = height / CM_IN_INCH / INCHES_IN_FOOT;
	printf("%.4f", height_in_feet);

	return 0;
}
```

# Q3

```c
#include <stdio.h>

int main() {
	int num;
	scanf("%d", &num);

	printf("%d", num%2);
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

# Q5

```c
#include <stdio.h>

int main() {
	int x, y, z;
	scanf("%d %d %d", &x, &y, &z);
	
    int result = (x%2) * x + (y%2) * y + (z%2) * z;
	printf("%d", result);

	return 0;
}
```

