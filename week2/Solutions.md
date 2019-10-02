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

### Q1

```c 
#include <stdio.h>

int main() {
    float pi = 3.14;
    float radius;          /* radius of the sphere */
	float volume;          /* volume of the sphere */

	printf("Input the radius of the sphere : ");
	scanf("%f", &radius);

	volume = (4.0 / 3.0) * pi * (radius * radius * radius);  
	printf("The volume of sphere is %f.\n", volume);

	return(0);
}
```



### Q2

```c 
#include <stdio.h>

int main(void)
{
  	float fahr, celsius;
  	int lower, upper, step;
    
	fahr = 0;
    celsius = (5.0/9.0) * (fahr - 32.0);
    printf("%3.1f %6.2f\n", celsius, fahr);
   
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
	
	h = (sec/3600); 
	
	m = (sec -(3600*h))/60;
	
	s = (sec -(3600*h)-(m*60));
	
	printf("H:M:S - %d:%d:%d\n",h,m,s);
	
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
	h = sec/3600;
	m = (sec%3600)/60;
	s = sec%60;
    
    	printf("H:M:S - %d:%d:%d\n",h,m,s);
	return 0;
}
```



### Q4

``` c 
#include <stdio.h>
int main()  
{  
    int angle1, angle2, angle3; /*are three angles of a triangle  */
  
    /* Read two angles of the triangle from user separated by comma*/  
    printf("Input two angles of triangle separated by comma : ");  
    scanf("%d, %d", &angle1, &angle2);  
  
    angle3 = 180 - (angle1 + angle2);  /* Calculates the third angle  */
  
    printf("Third angle of the triangle :  %d\n", angle3);  
  
    return 0;  
}  
```

