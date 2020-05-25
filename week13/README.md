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

    

### Question 1

Define a **struct** representing a point (x, y). 

* write a function **distance** which takes two points and finds Euclidean distance between these points.  Use *pow()* and *sqrt()* functions from math library *`include <math.h>`*
* write a function which takes two points and returns the point closest to the origin. *Use the distance function.*

In main function, take two points from user and prints the coordinates of the point. 

| Input          | Output |
| -------------- | ------ |
| 3 0<br />0 4   | 3 0    |
| 11 7 <br />6 8 | 6 8    |

### Question 2

Define a **struct** representing a rectangle that are parallel to the axes in a Cartesian coordinate system. Represent a rectangle by its lower left and upper right endpoints using the Point you defined. 

Write a function **move** which takes a rectangle pointer and two integers **moveX** and **moveY** representing the movement in the x and y axes respectively and moves the rectangle. 

**Example**:

* Rectangle:
  * lower left point: (2, 0)
  * upper right point: (8,  4)
* moveX: -5
* moveY: 2
* Resulting Rectangle:
  * lower left point: (-3, 2)
  * upper right point: (3,  6)

### Question 3

Write a program which takes an integer N and  reads N points (given by their x and y coordinates) and determines the pair that is the farthest apart. 

*Use the point definition and distance function from the first question*

| Input                                        | Output        |
| -------------------------------------------- | ------------- |
| 3<br/>3 0<br/>0 0<br/>0 4                    | 0,4<br/>3,0   |
| 5 <br/>10 5<br/>4 8<br/>0 8<br/>4 5<br/>-1 2 | -1,2<br/>10,5 |

### Question 4

Define a **struct** representing a student having **student_id (integer), mt_grade (integer), final_grade (integer) and letter_grade (char)**. The given program takes the grades of students and creates structs for students. You are supposed to calculate and set the letter grades of students using **set_grade() function**. The grade weights are 40%, 60% respectively and letter grades are as follows:

- 100-75: A
- 74-50: B
- 49-25: C
- 24-0: F 

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

### Question 5

Define a struct representing a flight which has following fields:

* Flight number (int)
* Originating airport code (three characters)
* Destination airport code (three characters)
* Starting time (int)
* Arrival time (int)

Write a function which reads a flight from user. 

Write a program that takes an integer N and then reads N flights. Then reads originating and destination airport code from user and lists all the planes that leave from the originating airport and arrive at the destination airport.

| Input                                                        | Output                                     |
| ------------------------------------------------------------ | ------------------------------------------ |
| 5<br/>3540 SAW ADB 14 15<br/>3440 IST ESB 13 15<br/>4041 ANT STL 13 21<br/>4045 GTG KPG 17 18<br/>ANT STL | 4041 ANT STL 13 21                         |
| 4<br/>3540 SAW ADB 14 15<br/>3543 SAW ADB 21 22<br/>3440 IST ESB 13 15<br/>4045 JFK IST 9 19<br/>SAW ADB | 3540 SAW ADB 14 15<br />3543 SAW ADB 21 22 |

### Question 6

Write a program which takes an integer N and then reads N flights. Then sorts the flights according to their starting time and the originating airport code. 

*Use the definition and functions from Question 5* 

| Input                                                        | Output                                                       |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| 4<br />3540 SAW ADB 14 15<br/>3440 IST ESB 13 15<br/>4041 ANT STL 13 21<br/>4045 GTG KPG 17 18 | 4041 ANT STL 13 21<br/>3440 IST ESB 13 15<br/>3540 SAW ADB 14 15<br/>4045 GTG KPG 17 18 |

*Hint: Write a function for comparing two flights. It first checks the starting times and if they are equal then compares the originating airport codes.*

 ## Question 7 (Teaching.Codes - Lab 10 - Question 2)

Define a struct named: Person which has an age, and a salary. Define a struct named: Family which has up to 9 persons and personCount (integer).

Write a function which takes 3 families, and returns the age of the person who earns the most in the family with the least total salary. (age of the richest person in the poorest family)

