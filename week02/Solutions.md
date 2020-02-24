# Solutions

## Warm Up

```c
#include <stdio.h> 
int main() 
{
    printf("*   *\n");
    printf(" * *\n");
    printf("  *\n");
    printf(" * *\n");
    printf("*   *\n");
    return(0);
}
```



```c
#include <stdio.h> 
int main() 
{
    printf("######\n");
    printf("#\n");
    printf("#\n");
    printf("#####\n");
    printf("#\n");
    printf("#\n");
    printf("#\n");
    return(0);
}
```

## Warm Up

```c
#include <stdio.h> 
int main() 
{
   	int num1, num2;
	scanf("%d%d", &num1, &num2);
	// printf("%d %d ", num1, num2); // Prints inputs
	printf("%d", num1 * num2);
	return 0;
}
```

#### Alternative

```c
#include <stdio.h> 
int main() 
{
   	int num1, num2;
	scanf("%d%d", &num1, &num2);
	int product = num1 * num2;
    printf("%d", product);
	return 0;
}
```

### Q1

```c 
#include <stdio.h>

int main() {
    float pi = 3.14;
    float radius;          /* radius of the sphere */
	float volume;          /* volume of the sphere */

	printf("Input the radius of the sphere : ");
	scanf("%f", &radius);

	volume = 4.0 / 3 * pi * (radius * radius * radius);  
	printf("The volume of sphere is %f.\n", volume);

	return 0;
}
```



### Q2

```c 
#include <stdio.h>

int main(void)
{
	float fahr;
	scanf("%f", &fahr);
	int celc = (fahr - 32) * 5.0 / 9;
	printf("%d", celc);
	return 0;
}
```

### Q3

``` c
#include <stdio.h>
int main() {
	int sec, h, m, s;
	printf("Input seconds: ");
	scanf("%d", &sec);
	
	h = sec / 3600; 
	
	m = (sec - (3600 * h)) / 60;
	
	s = (sec - (3600 * h) - (m * 60));
	
	printf("H:M:S - %d:%d:%d\n", h, m, s);
	
	return 0;
}
```

#### Alternative solution

``` c
#include <stdio.h>
int main() {
	int sec, h, m, s;
	printf("Input seconds: ");
	scanf("%d", &sec);
    
	// total seconds = 3600 * hours + 60 * minutes + seconds 
	h = sec / 3600;
	m = (sec % 3600) / 60;
	s = sec%60;
    printf("H:M:S - %d:%d:%d\n", h, m, s);
	return 0;
}
```



### Q4

``` c 
#include <stdio.h>
int main()  
{  
	int n1, n2, n3;
	scanf("%d%d%d", &n1, &n2, &n3);
	n1 = n1 * (n1 % 2) ;
	n2 = n2 * (n2 % 2);
	n3 = n3 * (n3 % 2);
	printf("%d", n1+n2+n3);
	return 0; 
}  
```

#### Alternative Solution

```c
#include <stdio.h>
int main()  
{  
	int n1, n2, n3;
	scanf("%d%d%d", &n1, &n2, &n3);
	printf("%d", n1 * (n1 % 2) + n2 * (n2 % 2) + n3 * (n3 % 2));
	return 0; 
}  	

```

