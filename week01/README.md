# Welcome to CMPE150.04 Lab Session!

### Assistant: Gökçe Uludoğan

### Mail:		   gokce.uludogan@boun.edu.tr

### Office:	    BM36

## Github:	https://github.com/gokceuludogan/cmpe150 

## Important Announcements

* You will be added to an email list for the announcements after the add/drop period. **Make sure that your e-mail in BUIS is valid! **

* We will use **Eclipse IDE** and **Teaching Codes** plug-in in labs and exams.  Student accounts will be created for this plug-in. The username and password will be sent to **the e-mail in BUIS**.

* There will be **weekly quizzes** during lab hours.  The quiz grades **contribute** to the overall grade. 

* Everyone must attend to the lab session of **the section registered to**.  If you have any conflict, you should change your section. 

* You should complete the installation as soon as possible after we send the manual. 

* Labs hours are dedicated to **practical programming exercises not for covering lecture materials**. I **strongly** suggest you to attend the lectures. 

  

# Programming Languages

![Image result for popular programming languages](https://www.ubuntupit.com/wp-content/uploads/2018/11/Most-Popular-Programming-Languages.jpg)

Figure from: https://www.ubuntupit.com/wp-content/uploads/2018/11/Most-Popular-Programming-Languages.jpg

![1569351507071](figures/1569351507071.png)



## Installation

**Manuals:** https://programming.cmpe.boun.edu.tr/welcome

The installation consists of four stages. The steps you should follow for these stages are OS dependent (Windows, Linux, MacOS). 

* **Stage #1:** *Install Java 8u181 JDK*
* **Stage #2:** *Installing the C Compiler*
* **Stage #3:** *Download and Install the ZIP File*
* **Stage #4:** *Run Eclipse and Set Your Workspace*



## Eclipse IDE

### What's an IDE? 

An integrated development environment (**IDE**) is a software application that provides comprehensive facilities to computer programmers for software development. An **IDE** normally consists of at least a source code editor, build automation tools, and a debugger. (Definition from https://en.wikipedia.org/wiki/Integrated_development_environment)

### Eclipse is an open source integrated development environment. 

It provides tools for *writing code, compiling and building the program and debugging.*



## User Interface 

![1569348487515](figures/1569348487515.png)



* Project Explorer

  ![1569348386213](figures/1569348386213.png)

  

  

  

  

* Code Editor

  ![1569348513992](figures/1569348513992.png)

  

  

  

* Teaching Codes Plug-in

  ![1569348537826](figures/1569348537826.png)

  

  

  

* Console

  ![1569348574235](figures/1569348574235.png)

  

  

  

* Toolbar

  ![1569348604330](figures/1569348604330.png)

  
  
  
  
  

 **If you closed any of these views accidentally, you can open them following *Window>Show View> (View Name) (i.e. Console, Project Explorer, Other for Teaching Codes)* **



### Creating a New Project and Running

* Click **New** Under **File**.
* Choose **C/C++ Project**. 
* Choose **C Managed Builds**. 
* Give your project a *name* and click **Finish**. 
* To build and run your project for the first time, you should right click on the project on *Project Explorer*. 
* Click **Build Project** from the options.
* After you see *Build Finished* message on the *Console*, right click on the project again. 
* Click **Run as Local C/C++ Application**.  
* After first building and running, you could use the **build** and **run** buttons on the *Toolbar*. 

## Main Function 

* This function is "called" by the operating system when the program runs. Thus it is the first code executed when a program starts. 
* Statements are executed in sequential order.

* **return 0;**  terminates the main() function and returns the value 0 meaning that the program runned successfully.

## Comments

* Multiline comments: /* */

* Single line comments:  //

## Code Block 

* The set of statements between a pair of braces is called a *block*.

* Each statement must end with a semicolon (;)

## Variables

* Storing value for later use
* Variable names: only letters (English), digits, and underscore ( _ ). cannot start with a digit. Case sensitive.

## Declarations

* In C, every variable needs to be *declared* to be a specific type before use. (i.e. int sum;)
* Several variables of the same type can be declared in a single line. Names separated with comma. (int num1, num2, num3;)

### Example

```c
#include <stdio.h>
int main()
{
    int num1;
    int num2;
    int num3, num4;
    return 0;    
}
```

## Assignments (=)

* Stores a value at the memory location reserved for the variable. **Not mathematical equality.**

### Example

```c
#include <stdio.h>
int main()
{
    int num1;
    num1 = 3;
    int num2 = 5;
    return 0;    
}
```

## Operations 

* Sum, Subtraction, Multiplication, Division, Modulus. 

### Example

```c
#include <stdio.h>
int main()
{
    int num1 = 3;
    int num2 = 5;
    int num3;
    num3 = num1 + num2;
    return 0;    
}
```

## Conventions

* Write one statement per line
* Indent the code inside a block (press Tab).
* Blocks inside blocks should be further indented.
* Use spaces on both sides of operators.
* Use a lot of comments.
* Use meaningful variable names.

## Output

* The #include directive copies the contents of a “header file” into source code.
* stdio.h: The header file for the standard input-output library.
* Required for the printf() function.
* #include <stdio.h>

### printf() 

* printf(“Result= %d\n”, num3);
* Takes a “format string”, and any number of expressions. Expression: Anything that returns a value.
* %d: “Format specifier”, used for int.
* \n: Newline character (one of the “escape” characters)
* printf(“%d + %d = %d\n”, num1, num2, num3);**

### Example

```c
#include <stdio.h>
int main()
{
    printf("Hello world!");
    return 0;    
}
```

### Example

```c
#include <stdio.h>
int main()
{
    int num1 = 3;
    int num2 = 5;
    int num3;
    num3 = num1 + num2;
    printf(“%d + %d = %d\n”, num1, num2, num3);
    return 0;    
}
```

## Input

- Format: ```scanf("%d", &number);```  *the variable **number** must be declared before.*
- Requires  *stdio.h*: ```#include <stdio.h>```

```c
#include <stdio.h>
int main(){
    // Declare variables
    int number_1, number_2, product;
    //Read first value
    printf("Enter first number\n");
    scanf("%d", &number_1);
    //Read second value
    printf("Enter second number\n");
    scanf("%d", &number_2);
    product = number_1 * number_2;
    // Display output
    printf("The product of %d and  %d is %d\n", number_1, number_2, product);
    return 0;
}
```

### 











