# Cmpe150 Functions

* A group of programming statements

* Take **Parameters**

* **Return** Value

* **Called**

  ```c
  function_name(parameter1, parameter2);
  ```

* Syntax

  ```c
  return_type function_name(parameter_list) {
      local_variable_definitions
      statements
      return return_value
  }
  ```

  * **parameter-list:** is zero, one, or more variables (**type**
    and **name**) that holds the data passed to the function
    when it is called
    *  may or may not be altered by the function
  * **return-type** specifies the type of the data that
    function returns to the instruction that called this function
    * if missing, int.
    * The type **must match** the return type specified in the function header. 

* Parameter vs Argument

  * A parameter declares the type and name of a variable that generalizes the function behavior; It is a **placeholder** for some unspecified value.
    * int find_max(int num1, int num2, int num3)
  * An argument is the actual value passed by the caller to the function when it invokes the function. It indicates the specific behavior of the
    function.
    * find_max(5, 3, 8);

  #### Question 1

  * Write a function **find_max()** which takes three integers as parameters and returns **maximum** among them. Then, call this function in main() function with the following inputs and print corresponding outputs.

  * ```
    input: 5, 3, 8
    output: 8
    
    input: 14, -1, 9
    output: 14
    ```

  ## Void functions

  * a function that does **not return a value**.

    ```c
    void function_name(parameters){
        statements
    }
    ```

  * For displaying on screen, input/output operations

  ### Passing parameters by value

  * In a function call, the value of the parameter is **copied** to a
    local variable (For now).
  * Any changes in variables inside function remains in this function's scope (Until it dies!). 

  ### Local Variable

  * A variable declared in the function is called a local variable. It can be used only inside the function

  ### Global Variable

  * A **global variable** is a **variable** that is declared outside all functions
  * It can be used in all functions below its definition.

  ### Scope

  * The scope of a variable determines where the variable is visible.
  * The scope of a local variable starts from where the variable is declared to the end of the block in which it is declared. 
  * **The scope of a function parameter is the function body.**

  ### Lifetime

  * When the function terminates, all of the local variables (and
    their values) are lost.
  * When the function is called again, all variables start from scratch (except static ones)
  * The lifetime of a global variable is the lifetime of the program.

  ### Shadowing definition

  * Local definition shadows global definition
  * Parameter definition shadows global definition

  ### Static Variables

  * It is used when we want to retain the value of a local variable between calls. 
  * ``` static int variable_name = value;```
  * the lifetime of the program.
  * local variables
  * The declaration and initialization line is used only in the first call of the function.

  #### Question 2

  Write a function **to_upper()** which takes **a char** as input, and returns the upper case version of the character if it is a lower case letter. Otherwise it should return the same character.

  Then write a program which reads a word from the user, and prints it with upper case characters. Assume valid words will be given.

  ```c
  input:cmpe
  output:CMPE
  ```

  #### Question 3

  Write a function **factorial()** that takes an integer as a parameter and computes the factorial of that integer.

  Then, write a program to compute the summation of each digits' factorial using factorial function.

  ```c
  input: 43
  output: 30
  ```

  #### Question 4

  Write a function **is_prime()** that checks whether the given number is prime. The function returns 1 if the number is prime and returns 0 otherwise. Then write a program which takes an integer and prints all of its prime divisors. 

  ```
  input: 12
  output: 2 3
  ```

  ### Passing parameters by reference

  * We want to change the value of variable inside function.

  * We pass a reference to the parameter

    ```c
    void func(int *z)
    {
        (*z)++;
        printf("In func: %d\n", *z);
    }
    int main()
    {
        int a = 1;
        printf("%d\n", a);
        func(&a);
        printf("%d\n", a);
    }
    ```

  * ### **&**: address of operator

  * ### *****: value at address operator

![](figures/W08-ptr1.png)

![](figures/W08-ptr2.png)

![](figures/W08-ptr3.png)



#### Question 5

##### Write a function **find_min_max()** which takes three integers and two pointers as parameters and sets the max and min of these three integers to addresses pointed by these two pointers. 

