# Structures

* How can we keep data which is a combination of types?

* Structure!

  * A new data type

  * Definition:

    * ```
      struct cat {
      	char name[10];
      	int age;
      	char gender;
      };
      ```

  * Declaration

    * `struct cat x;`

  * Initialization at declaration

    * struct cat x = {"Yumuk", 3, 'M'};

  * Definition can be combined with declaration

    * ```c
      struct cat {
      	char name[10];
      	int age;
      	char gender;
      } pet1, pet2;
      ```

    * Which one is type/variable?

  * Accessing members 

    * Dot operator: *x.name* gives *Yumuk*

* **typedef operator**

  * new name for an existing data type

  * `typedef float real;`

  * with struct

    * ```c
      typedef struct cat {
      	char name[10];
      	int age;
      	char gender;
      } Cat_t;
      
      Cat_t x;
      ```

* Nested structures:

  * Structure inside structure

    * ```c
      typedef struct{
      	char name[10];
      	int age;
      	char gender;
      } Cat_t;
      
      typedef struct{
      	Cat_t animals[10];
      } Shelter_t;
      
      Shelter_t sh;
      sh.animals[0] = {"Tekir", 2, 'F'};
      ```

  * Access

    * `puts(sh.animals[0].name);`

* Function Parameters

  * Pass by value

    * ```c
      int same_age(Cat_t c1, Cat_t c2){
      	if(c1.age == c2.age){
      		return 1;
      	}else{
      		return 0;
      	}
      }
      int main(){
      	Cat_t c1 = {"Dana", 3, 'M'}, c2 = {"Yumuk", 3, 'M'};
      	printf("%d", same_age(c1, c2));
      	
      	return 0;
      }
      ```

  * Pass by reference

    * Similar to the basic types.

    * ```c
      void append_to_name(Cat_t *p, char second_name[]){
          strcat((*p).name, second_name);
      }
      ```

    * `append_to_name(&x, " Mars");`

* Structure as return value

  * ```c
    Cat_t create_cat(char name[], int age, char gender){
    	Cat_t c;
    	strcpy(c.name, name);
    	c.age = age;
    	c.gender = gender;
    	return c;
    }
    ```

  * `	Cat_t x = create_cat("Dana", 3, 'M');`

* Shortcut

  * `(*p).name` == `p->name`

* Passing arrays of structures to functions

  * Same as basic types. 

  * Pass by reference

  * ```c
    typedef struct{
        float x;
        float y;
    } Point_t;
    
    Point_t center(Point_t p[], int len){
        Point_t center_p = {0, 0};
        int i;
        for(i=0; i<len; i++){
            center_p.x += p[i].x;
            center_p.y += p[i].y;
        }
        
        center_p.x /= len;
        center_p.y /= len;
        return center_p;
    }
    ```

    

### Question

Define a **struct** representing a point (x, y). Then write a function which takes two points and finds Euclidean distance between these points.  Use *pow()* and *sqrt()* functions from math library *`include <math.h>`*

### Question 

Define a **struct** representing a rectangle that are parallel to the axes in a Cartesian coordinate system. Represent a rectangle by its lower left and upper right endpoints using the Point you defined. Write a function area_of_rectangle() that computes the area of a rectangle. 

### Question

Write a program that reads in a list of points (given by their x and y coordinates) and determines the pair that is the farthest apart.

### Question

Define a struct representing a flight which has following fields:

* Flight number
* Originating airport code (three characters)
* Destination airport code (three characters)
* Starting time
* Arrival time

Write a program that lists all the planes that leave from two airports specified by the user.

### Question

Define a **struct** representing a student having **student_id (integer), mt_grade (integer), final_grade (integer) and letter_grade (char)**. The given program takes the grades of students and creates structs for students. You are supposed to calculate and set the letter grades of students using **set_grade() function**. The grade weights are 40%, 60% respectively and letter grades are as follows:

* 100-75: A
* 74-50: B
* 49-25: C
* 24-0: F 

```c
#include <stdio.h>
#include <stdlib.h>

// Fills the definition of the struct.
typedef struct{
	
} Student;

void set_grade(Student *p){

}

int main(void){
	int N;
	scanf("%d", &N);
	Student cmpe150_students[N];
	int i;
	for(i=0; i < N; i++){
		scanf("%f%f", &cmpe[i].mt_grade, &cmpe[i].final_grade);
		cmpe[i].student_id = 1000 + i;
        // Call set grade function
	}
	return 0;
}
```

### Question

Write a program which sorts the flights according to their starting time and the  originating airport code. 

```
input:
TK3540 SAW ADB 14 15
TK3440 IST ESB 13 15
TK4041 ANT STL 13 21
TK4045 GTG KPG 17 18
output:
TK4041 ANT STL 13 21
TK3440 IST ESB 13 15
TK3540 SAW ADB 14 15
TK4045 GTG KPG 17 18
```

*Hint: Write a function for comparing two flights. It first checks the starting times and if they are equal then compares the originating airport codes.*

 

