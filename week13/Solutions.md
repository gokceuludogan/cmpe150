# Solutions

## Question 1

```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

struct point{
	float x;
	float y;
};

float distance(struct point p1, struct point p2){
	return sqrt(pow(p1.x - p2.x, 2) + pow(p1.y - p2.y, 2));
}

int main(){
	struct point p1, p2;
	scanf("%f %f", &p1.x, &p1.y);
	scanf("%f %f", &p2.x, &p2.y);
	printf("%f", distance(p1, p2));
	return 0;
}
```

### Alternative 

```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

typedef struct {
	float x;
	float y;
} Point_t;

float distance(Point_t p1, Point_t p2){
	return sqrt(pow(p1.x - p2.x, 2) + pow(p1.y - p2.y, 2));
}

int main(){
	Point_t p1, p2;
	scanf("%f %f", &p1.x, &p1.y);
	scanf("%f %f", &p2.x, &p2.y);
	printf("%f", distance(p1, p2));
	return 0;
}
```

## Question 2

```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

typedef struct {
	float x;
	float y;
} Point_t;

typedef struct{
	Point_t lower_left;
	Point_t upper_right;
} Rect_t;


float area(Rect_t r){
	return (r.lower_left.x - r.upper_right.x) * (r.lower_left.y - r.upper_right.y);
}

int main() {
	Rect_t r;
	scanf("%f %f", &r.lower_left.x, &r.lower_left.y);
	scanf("%f %f", &r.upper_right.x, &r.upper_right.y);
	printf("%f", area(r));
	return 0;
}

```

## Question 3

```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

typedef struct {
	float x;
	float y;
} Point_t;


float distance(Point_t p1, Point_t p2){
	return sqrt(pow(p1.x - p2.x, 2) + pow(p1.y - p2.y, 2));
}

int main() {
	int n,i,j;
	scanf("%d", &n);
	Point_t p_arr[n];
	for(i=0; i<n;i++){
		scanf("%f %f", &p_arr[i].x, &p_arr[i].y);
	}
	int max=0;
	Point_t p1, p2;
	for(i=0; i<n; i++){
		for(j=0 ;j<i; j++){
			int dist = distance(p_arr[i], p_arr[j]);
			if(dist > max){
				max = dist;
				p1 = p_arr[i];
				p2 = p_arr[j];
			}
		}
	}
	printf("p1 %.2f %.2f\n", p1.x, p1.y);
	printf("p2 %.2f %.2f", p2.x, p2.y);
	return 0;
}

```

## Question 4

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct{
	int flight_no;
	char orig[4];
	char dest[4];
	int start;
	int end;
} Flight_t;

int main(void) {

	Flight_t flights[5] = {{12, "ABC", "BCD", 14, 15},
			{13, "SAW", "ADB", 14, 15},
			{14, "SAW", "ESB", 14, 15},
			{15, "JFK", "IST", 14, 1},
			{16, "SAW", "ADB", 18, 19}
	};
	char orig[4], dest[4];
	scanf("%s", &orig);
	scanf("%s", &dest);
	int i;
	for(i=0; i<5; i++){
		if(strcmp(flights[i].orig, orig) == 0 && strcmp(flights[i].dest, dest) == 0){
			printf("%d %d\n", flights[i].flight_no, flights[i].start);
		}
	}

	return EXIT_SUCCESS;
}

```

## Question 5

```c
#include <stdio.h>
#include <stdlib.h>

// Fill the definition of the struct.
typedef struct{
    int student_id;
    float mt_grade;
    float final_grade;
    char letter_grade;
} Student;

void set_grade(Student *p){
	int total_grade = (*p).mt_grade * 0.4 + (*p).final_grade * 0.6;
	if(total_grade > 75){
		p->letter_grade = 'A';
	}else if(total_grade > 50){
		p->letter_grade = 'B';
	}else if(total_grade > 25){
		p->letter_grade = 'C';
	}else{
		p->letter_grade = 'F';
	}
}

int main(void){
    int N;
    scanf("%d", &N);
    Student cmpe[N];
    int i;
    for(i=0; i < N; i++){
        scanf("%f%f", &cmpe[i].mt_grade, &cmpe[i].final_grade);
        cmpe[i].student_id = 1000 + i;
        // Call set grade function
        set_grade(&cmpe[i]);
    }

    printf("%c", cmpe[0].letter_grade);
    return 0;
}
```

## Question 6

```c
/*
 ============================================================================
 Name        : w13_q4.c
 Author      : 
 Version     :
 Copyright   : Your copyright notice
 Description : Hello World in C, Ansi-style
 ============================================================================
 */

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct{
	int flight_no;
	char orig[4];
	char dest[4];
	int start;
	int end;
} Flight_t;

int compare_flights(Flight_t f1, Flight_t f2){
	if(f1.start == f2.start){
		return strcmp(f1.orig, f2.orig);
	}else{
		return f1.start - f2.start;
	}
}

int main(void) {
	int size = 4;
	Flight_t flights[] = {{3540, "SAW", "ADB", 14, 15},
			{3440, "IST", "ESB", 13, 15},
			{4041, "ANT", "STL", 13, 21},
			{4045, "GTG", "KPG", 17, 18}};

	int i, j;
	for(i=0; i<size; i++){
		for(j=i+1; j<size; j++){
			if(compare_flights(flights[i], flights[j]) > 0){
				Flight_t temp = flights[i];
				flights[i] = flights[j];
				flights[j] = temp;
			}
		}
	}

	for(i=0; i<size; i++){
		printf("%d %s %s %d %d\n", flights[i].flight_no, flights[i].orig, flights[i].dest, flights[i].start, flights[i].end);
	}

	return EXIT_SUCCESS;
}
```

