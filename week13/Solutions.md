# Question 1

```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

struct point{
	int x;
	int y;
};

float distance(struct point p1, struct point p2){
	return sqrt(pow(p1.x - p2.x, 2) + pow(p1.y - p2.y, 2));
}

struct point closest_to_origin(struct point p1, struct point p2){
	struct point origin = {0, 0};
	float p1_dist = distance(p1, origin);
	float p2_dist = distance(p2, origin);
	return p1_dist < p2_dist ? p1 : p2;
}

int main() {
	struct point p1;
	struct point p2;
	scanf("%d%d", &p1.x, &p1.y);
	scanf("%d%d", &p2.x, &p2.y);

	// printf("%f", distance(p1, p2));
	struct point closest = closest_to_origin(p1, p2);
	printf("%d %d", closest.x, closest.y);

	return 0;
}
```

# Question 2

```c
#include <stdio.h>
#include <stdlib.h>

struct point{
	int x;
	int y;
};

struct rectangle{
	struct point lower_left;
	struct point upper_right;
};


void move(struct rectangle* p, int moveX, int moveY){
	(*p).lower_left.x += moveX;
	(*p).upper_right.x += moveX;
	(*p).lower_left.y += moveY;
	(*p).upper_right.y += moveY;

	/*
	p->lower_left.x += moveX;
	p->upper_right.x += moveX;
	p->lower_left.y += moveY;
	p->upper_right.y += moveY;
	*/
}

int main() {
	struct rectangle r = {{2,0}, {8,4}};

	/*struct point p1 = {2, 0};
	struct point p2 = {8, 4};
	struct rectangle r = {p1, p2};*/


	/*struct point p1 = {2, 0};
	struct point p2 = {8, 4};
	struct rectangle r;
	r.lower_left = p1;
	r.upper_right = p2;*/


	/*struct rectangle r;
	r.lower_left.x = 2;
	r.lower_left.y = 0;
	r.upper_right.x = 8;
	r.upper_right.y = 4;*/


	move(&r, -5, 2);
	printf("%d,%d\n", r.lower_left.x, r.lower_left.y);
	printf("%d,%d", r.upper_right.x, r.upper_right.y);
	return 0;
}
```

# Question 3

```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

struct point{
	int x;
	int y;
};

float distance(struct point p1, struct point p2){
	return sqrt(pow(p1.x - p2.x, 2) + pow(p1.y - p2.y, 2));
}

int main(){
	int N, i, j;
	scanf("%d", &N);
	struct point points[N];
	for(i = 0; i < N; i++){
		scanf("%d%d", &points[i].x, &points[i].y);
	}

	float max = 0;
	int point1_ix, point2_ix;
	for(i = 0; i < N; i++){
		for(j = i+1; j < N; j++){
			float dist = distance(points[i], points[j]);
			if(dist > max){
				max = dist;
				point1_ix = i;
				point2_ix = j;
			}
		}
	}

	printf("%d,%d\n", points[point1_ix].x, points[point1_ix].y);
	printf("%d,%d", points[point2_ix].x, points[point2_ix].y);

	return 0;
}
```

## Alternative

```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

typedef struct point{
	int x;
	int y;
}Point_t;

float distance(Point_t p1, Point_t p2){
	return sqrt(pow(p1.x - p2.x, 2) + pow(p1.y - p2.y, 2));
}

void print_point(Point_t p){
	printf("x: %d y: %d\n", p.x, p.y);
}

int main(){
	int N, i, j;
	scanf("%d", &N);
	Point_t points[N];
	for(i = 0; i < N; i++){
		scanf("%d%d", &points[i].x, &points[i].y);
	}
	float max = 0;
	int point1_ix, point2_ix;
	for(i = 0; i < N; i++){
		for(j = 0; j < i; j++){
			float dist = distance(points[i], points[j]);
			if(dist > max){
				max = dist;
				point1_ix = i;
				point2_ix = j;
			}
		}
	}
	print_point(points[point1_ix]);
	print_point(points[point2_ix]);

	return 0;
}
```

# Question 4

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

int main(){
    int N;
    scanf("%d", &N);
    Student cmpe[N];
    int i;
    for(i=0; i < N; i++){
        scanf("%f%f", &cmpe[i].mt_grade, &cmpe[i].final_grade);
        cmpe[i].student_id = i;
        // Call set grade function
        set_grade(&cmpe[i]);
    }
    for(i=0; i < N; i++){
        printf("%c\n", cmpe[i].letter_grade);
    }
    return 0;
}
```

# Question 5

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct flight{
	int flight_no;
	char orig[4];
	char dest[4];
	int start;
	int end;
} Flight_t;

Flight_t read_flight(){
	Flight_t fl;
	scanf("%d %s %s %d %d", &fl.flight_no, fl.orig, fl.dest, &fl.start, &fl.end);
	return fl;
}

void print_flight(Flight_t f){
	printf("%d %s %s %d %d\n", f.flight_no, f.orig, f.dest, f.start, f.end);
}

int main() {
	int N, i;
	scanf("%d", &N);
	Flight_t flights[N];
	for(i = 0; i < N; i++){
		/*scanf("%d %s %s %d %d", &flights[i].flight_no,
				flights[i].orig, flights[i].dest,
				&flights[i].start, &flights[i].end);
		*/
		flights[i] = read_flight();
	}
	char orig[4], dest[4];
	scanf("%s %s", orig, dest);
	for(i = 0; i < N; i++){
		if(strcmp(flights[i].orig, orig) == 0 && strcmp(flights[i].dest, dest) == 0){
			print_flight(flights[i]);
		}
	}

	return 0;
}

```

# Question 6

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

Flight_t read_flight(){
	Flight_t fl;
	scanf("%d %s %s %d %d", &fl.flight_no, fl.orig, fl.dest, &fl.start, &fl.end);
	return fl;
}

void print_flight(Flight_t f){
	printf("%d %s %s %d %d\n", f.flight_no, f.orig, f.dest, f.start, f.end);
}

int compare_flights(Flight_t f1, Flight_t f2){
	if(f1.start == f2.start){
		return strcmp(f1.orig, f2.orig);
	}else{
		return f1.start - f2.start;
	}
}

int main() {
	int N, i, j;
	scanf("%d", &N);
	Flight_t flights[N];
	for(i = 0; i < N; i++){
		flights[i] = read_flight();
	}

	for(i = 0; i < N; i++){
		for(j = i+1; j < N; j++){
			if(compare_flights(flights[i], flights[j]) > 0){
				Flight_t temp = flights[i];
				flights[i] = flights[j];
				flights[j] = temp;
			}
		}
	}

	for(i=0; i < N; i++){
		print_flight(flights[i]);
	}

	return 0;
}

```

# Question 7

```c
#include <stdio.h>
#include <stdlib.h>

struct Person{
	int age;
	int salary;
};

typedef struct Family{
	struct Person persons[9];
	int personCount;
} Fam_t;

int poorest_family(Fam_t f[], int size){
	int min_salary;
	int i, j, index = -1;
	for(i = 0; i < size; i++){
		int total = 0;
		for(j = 0; j < f[i].personCount; j++){
			total += f[i].persons[j].salary;
		}
		if(i == 0){
			min_salary = total;
		}else if(total < min_salary){
			min_salary = total;
			index = i;
		}
	}
	return index;
}

int richest_member(struct Family f){
	int i, max = 0, index = -1;
	for(i = 0; i < f.personCount; i++){
		if(f.persons[i].salary > max){
			max = f.persons[i].salary;
			index = i;
		}
	}
	return index;
}

/*
SAMPLE INPUT
3
10 0 33 5000 34 5500
5
10 10 30 1100 45 500 67 1000 5 0
2
48 4800 50 5000
*/
int main() {
	struct Family families[3];
	int i, j;
	for(i = 0; i < 3; i++){
		scanf("%d", &families[i].personCount);
		for(j = 0; j < families[i].personCount; j++){
			scanf("%d%d", &families[i].persons[j].age, &families[i].persons[j].salary);
		}
	}
	int poorest = poorest_family(families, 3);
	int richest = richest_member(families[poorest]);
	printf("Richest person in the poorest family is %d years old.\n", families[poorest].persons[richest].age);
	return 0;
}
```

