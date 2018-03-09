# Lab 07: Implementing Dynamic Arrays in C++

### Description

This week in class you learned about memory allocation and linked lists. In today's lab you will be implementing a **Dynamic Array**.
The starter code for this lab can be found above (You need the 3 files: **darray.h, darray.cc, and main.cc**). You may work in groups of 2 to 3. 


### Dynamic Arrays

As you know by now, when an array is created in C++ a set amount of memory is allocated for the array to use. For example, both of the following array declarations allocate exactly enough memory to store 6 integers:

```C++
int array_a[6]; // This array on the stack can hold 6 ints
int array_b = new int[6]; // This array on the heap can also hold 6 ints
```

However, in some languages, such as JavaScript, arrays can change size whenever needed. These kinds of arrays are called **Dynamic Arrays**, and in many situations Dynamic Arrays are much easier to work with. Generally Dynamic Arrays accomplish their resizing behavior by having a capacity variable that represents *the number of elements it is able to store* in its internal array. When an element is being added to a Dynamic Array that can hold no more elements, the capacity is doubled, a new array is created with the new capacity, and all of the elements are copied from the old array to the new array. This new array then becomes the one used by the Dynamic Array.

In addition to having the ability to change size, Dynamic Arrays also tend to provide many methods for accessing and modifying their content, providing further ease of use. In today's lab you will need to implement the following methods for your own Dynamic Array class. The class structure is already provided in `darray.h`.

#### Constructors/Destructors:

+ `DArray()`: A basic constructor to initialize the class' private variables. Your capacity (`cap`) may be initialized as 10.
+ `DArray(int c)`: A constructor similar to the `DArray()`, but with the capacity specified by the parameter `c`.
+ `~DArray()`: A destructor to deallocate the memory used by the class instance when it is destroyed.

#### Helper Methods:

+ `grow()`: A helper method that doubles the size of the internal array when an element is being added to a Dynamic Array that can hold no more elements.
+ `shrink()`: A helper method that does the opposite of grow, reducing the size when the DArray is half full or less.
+ `index_in_bounds(int idx)`: A helper method to test if 0 <= idx < length.

#### Accessors:

+ `size()`, `capacity()`, `front()`, and `back()`: Accessor methods that return the length, capacity, first element, and last element respectively.
+ `at(int idx)`: Returns the element at index `idx`.
+ `empty()`: Returns whether or not the Dynamic Array has no elements.

#### Modifiers:

+ `set(int elem, int idx)`: Sets the value of the Dynamic Array at the index `idx` to the value `elem`.
+ `push_back(int elem)`: Inserts `elem` at the end of the Dynamic Array.
+ `pop_back()`: Removes the element at the end of the Dynamic Array and returns it.
+ `insert(int elem, int idx)`: Inserts `elem` into the Dynamic Array at index `idx`.
+ `erase(int idx)`: Removes the element at the index `idx` from the Dynamic Array

**Note:** You need to check for valid input in the functions `at()`, `set()`, `pop_back()`, `insert()` and `erase()`. You should use `assert()` from the library `<cassert>` and `index_in_bounds()` as needed. 

## Instructions

Download the 3 files: dll.h, dll.cc, and main.cc

To compile your program, run the following command in your bash terminal:
```
g++ -std=c++11 darray.cc main.cc -o lab8
```
To run your program, run the following command
```
./lab8
```
You will be writing the unimplemented functions in the `DArray` class. You can run the main method in `main.cc` to test the functions as you implement them.