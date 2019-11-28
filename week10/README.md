# Cmpe150 Week10



#### Question

Write two functions **read_array()** and **print_array()** both of which take two parameters: integer array and the size of the array.

```
read_array() fills an array of integers size of M.
print_array() prints an array of integers size of M.
```

#### Question

Write a program reads an integer N from the user, then reads N integers from the user. Then checks whether the array is symmetric. Use **read_array()**. 

```c
input: 
7
10 3 -1 5 -1 3 10
output: symmetric
input: 
5
1 3 5 2 0
output: not symmetric
```

#### Question

Write a program reads two integers N1, N2 from the user, then reads N1 and N2 integers from the user to create two arrays. Then print common (included in both arrays) elements and their indices in the first array. Use **read_array()**. 

```
input:
6 8
2 5 10 53 17 8
-1 6 5 87 2 17 49 7
output: 
2 0
5 1
17 4
```

#### Question

Write a program reads an integer N from the user. Takes N integers from user and place them in an array. Then, print the maximum number of repeating elements successively and this repeating element. Use **read_array()**

```
input:
7
10 2 4 4 5 5 5
output:
3 5
input: 
13
8 8 8 8 2 2 4 4 4 5 5 2 9
4 8
```

#### Question

Write a function named **delete_element** which takes an array, length of this array and a index as parameters and deletes the element at desired position from the array. (Try with const. What happens?)

```
input: {1, 5, 6, 8, 9} 5 2
output: {1, 5, 8, 9}
```

#### Question

Write a program reads two integers N1, N2 from the user, then reads N1 and N2 integers from the user to create two arrays. Then delete common (included in both arrays) elements from the first array and print this array.

```
input:
6 8
2 5 10 53 17 8
-1 6 5 87 2 17 49 7
output: 
2 10 53 17 8
```

 