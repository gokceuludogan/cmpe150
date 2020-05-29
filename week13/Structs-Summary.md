- How can we keep data which is a combination of types?

- Structure!

  - A new data type

  - Definition:

    - ```
      struct cat {
      	char name[10];
      	int age;
      	char gender;
      };
      ```

  - Declaration

    - `struct cat x;`

  - Initialization at declaration

    - struct cat x = {"Yumuk", 3, 'M'};

  - Definition can be combined with declaration

    - ```c
      struct cat {
      	char name[10];
      	int age;
      	char gender;
      } pet1, pet2;
      ```

    - Which one is type/variable?

  - Accessing members 

    - Dot operator: *x.name* gives *Yumuk*

- **typedef operator**

  - new name for an existing data type

  - `typedef float real;`

  - with struct

    - ```c
      typedef struct cat {
      	char name[10];
      	int age;
      	char gender;
      } Cat_t;
      
      Cat_t x;
      ```

- Nested structures:

  - Structure inside structure

    - ```c
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

  - Access

    - `puts(sh.animals[0].name);`

- Function Parameters

  - Pass by value

    - ```c
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

  - Pass by reference

    - Similar to the basic types.

    - ```c
      void append_to_name(Cat_t *p, char second_name[]){
          strcat((*p).name, second_name);
      }
      ```

    - `append_to_name(&x, " Mars");`

- Structure as return value

  - ```c
    Cat_t create_cat(char name[], int age, char gender){
    	Cat_t c;
    	strcpy(c.name, name);
    	c.age = age;
    	c.gender = gender;
    	return c;
    }
    ```

  - `	Cat_t x = create_cat("Dana", 3, 'M');`

- Shortcut

  - `(*p).name` == `p->name`

- Passing arrays of structures to functions

  - Same as basic types. 

  - Pass by reference

  - ```c
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

    