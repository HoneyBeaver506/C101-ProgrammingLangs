---
Title: C++ Storage Data Types
Topic: Clang Learning Curve
aliases:
  - CStorageTypes
tags:
  - type/note
  - type/sketchnote
template-type: Back Matter
template_version: "1.12"
template-version: "1.0"
Created At: Sunday, June 1st 2025, 8:49:55 pm
Modified At: Thursday, June 5th 2025, 1:31:26 pm
created: 2025-06-01T20:49
updated: 2025-06-06T23:40
---
# I. C++ Storage Data Types
## II. Arrays
> [!Syntax] Syntax: Array
> datatype arrayName[arraySize];

`int x[6];`
- `int` - Type of element stored
- `x` - name of the array
- `[6]` - size of the array

**Array Index**: Each element in the array is associated with a number. These elements can be accessed with indicies
```cpp
// syntax to access array elements
array[index];
// or
array[4];
```

![[C++ Storage Data Types 2025-06-03 20.44.45.excalidraw]]

*To initialize an array*:
	Provide the array name, size and the elements used:
```cpp
int x[6] = {6, 7, 8, 9, 10, 11};
// Or, Can initialize without size, making it expandable as items are added to the array
int x[] = {6, 7, 8, 9, 10, 11};
```

*If the array is initialized with a size, but the designated items are less then the designated:*
	The compiler will automatically assign a random value. The default random value is 0.
	Out of bounds array will be interpreted as undefined. For example if the loop has 10 in its size, it will contain elements from 0 to 9. if 10 elements are added or more, this will print an error.
```cpp
int x[4] = {1, 2, 3};
// Compiler will assign random value
int x[4] = {1, 2, 3, 0};
```

*How to insert and print elements of an array:*
```cpp
int mark[5] = {19, 10, 8, 17, 9}

// change 4th element to 9
mark[3] = 9;

// take input from the user
// store the value at third position
cin >> mark[2];


// take input from the user
// insert at ith position
cin >> mark[i-1];

// print first element of the array
cout << mark[0];

// print ith element of the array
cout >> mark[i-1];
```

**Example 1: Displaying Array Elements**
```cpp
#include <iostream>
using namespace std;

int main() {

  int numbers[5] = {7, 5, 6, 12, 35};

  cout << "The numbers are: ";

  //  Printing array elements
  // using range based for loop
  for (int n : numbers) {
    cout << n << "  ";
  }

  cout << "\nThe numbers are: ";

  //  Printing array elements
  // using traditional for loop
  for (int i = 0; i < 5; ++i) {
    cout << numbers[i] << "  ";
  }

  return 0;
}
```
- The following example uses the classic for loop to iterate through the items inside of the array. 

**Example 2: Take inputs from the User and Store Them in an array**
```cpp
#include <iostream>
using namespace std;

int main() {

  int numbers[5];

  cout << "Enter 5 numbers: " << endl;

  //  store input from user to array
  for (int i = 0; i < 5; ++i) {
    cin >> numbers[i];
  }

  cout << "The numbers are: ";

  //  print array elements
  for (int n = 0; n < 5; ++n) {
    cout << numbers[n] << "  ";
  }

  return 0;
}
/* 
Enter 5 numbers: 
11
12
13
14
15
The numbers are: 11  12  13  14  15
*/
```
- Here, the input of the user is iterated and added to the array. This uses two. One to add the items into the array one by one and the other to print each element of the array with spaces.

**Example 3: Display the sum and average of array elements using a for loop**:
```cpp
#include <iostream>
using namespace std;

int main() {
    
  // initialize an array without specifying size
  double numbers[] = {7, 5, 6, 12, 35, 27};

  double sum = 0;
  double count = 0;
  double average;

  cout << "The numbers are: ";

  //  print array elements
  // use of range-based for loop
  for (const double &n : numbers) {
    cout << n << "  ";

    //  calculate the sum
    sum += n;

    // count the no. of array elements
    ++count;
  }

  // print the sum
  cout << "\nTheir Sum = " << sum << endl;

  // find the average
  average = sum / count;
  cout << "Their Average = " << average << endl;

  return 0;
}
/* 
The numbers are: 7  5  6  12  35  27
Their Sum = 92
Their Average = 15.3333
*/
```
Let's break down this explanation of working with an array, step by step, for a beginner.

---

## Understanding Arrays

Imagine you have a list of things you want to keep together, like a list of your daily expenses, or a list of scores from a game. In programming, an **array** is a way to store multiple items of the **same type** in a single variable. Think of it like a row of mailboxes, where each mailbox holds a piece of data.

## Initializing an Array Without a Specified Size

The first sentence says, "We have initialized a **`double` array named `numbers` but without specifying its size.**"

When you **initialize** an array, you're giving it its starting values. For example, if you wanted to store the numbers 10.5, 20.0, and 15.2, you could directly put those values into the array when you create it.

If you don't tell the computer exactly how many "mailboxes" (or spaces) the array needs when you first create it, the computer will automatically figure out the size based on how many values you give it right then. So, if you say `double numbers = {10.5, 20.0, 15.2};`, the computer knows `numbers` is an array of `double`s and it has a size of 3.
## Range-Based `for` Loop

"Then we used a **range-based `for` loop to print the array elements**. In each iteration of the loop, we add the current array element to `sum`."

A **loop** is a programming tool that allows you to repeat a block of code multiple times. A **`for` loop** is one type of loop. A **range-based `for` loop** is a special kind of `for` loop that's perfect for going through every item in a collection (like an array or a list).

Think of it like this: "For **each** number in the `numbers` array, do these steps..."

So, the loop will go through each `double` value in the `numbers` array, one by one. For each number it encounters:

- It **prints** that number to show you what's in the array.
- It **adds** that number to our `sum` variable. So, if `sum` was 0 and the first number is 10.5, `sum` becomes 10.5. If the next number is 20.0, `sum` becomes 10.5 + 20.0 = 30.5, and so on.
## Incrementing `count`

"We also **increase the value of `count` by 1 in each iteration**, so that we can get the size of the array by the end of the `for` loop."

In every single pass through the loop (for each number in the array), we do two things: add the number to `sum` and also add 1 to `count`.

- If the loop processes the first number, `count` becomes 1.
- If it processes the second number, `count` becomes 2.
- ...and so on.

By the time the loop finishes (meaning it has looked at every number in the array), the `count` variable will hold the **total number of elements** in the array. This is super useful because we didn't explicitly specify the arr
## Calculating and Printing Sum and Average

"After printing all the elements, we print the sum and the average of all the numbers. The average of the numbers is given by **`average = sum / count;`**"

Once the loop is finished, we have:

- **`sum`**: The total of all the numbers in the array.
- **`count`**: The total number of numbers in the array.

To find the **average**, you simply divide the total `sum` by the `count` of items. This result is then stored in the `average` variable, and finally, these results are displayed to you.

In short, this block of code effectively reads a list of numbers, calculates their total, counts how many there are, and then gives you the average!

----
# Passing Array to a Function in C++ Programming

> [!Syntax] 🔖 Syntax: 
> `return type functionName(dataType arrayName[]) { ... }`

**Example 1: Display 5 items of an array**
```cpp
// C++ Program to display marks of 5 students

#include <iostream>
using namespace std;

const int ARRAY_SIZE = 5;

// declare function to display marks
// take a 1d array as parameter
void display(int m[]) { // helpful to save time and mem
    cout << "Displaying marks: " << endl;

    // display array elements    
    for (int i = 0; i < ARRAY_SIZE; ++i) {
        cout << "Student " << i + 1 << ": " << m[i] << endl;
    }
}

int main() {

    // declare and initialize an array
    int marks[ARRAY_SIZE] = {88, 76, 90, 61, 69};
    
    // call display function
    // pass array as argument
    display(marks);

    return 0;
}
```

`new int[]` -> Works to create a new array as-well

----
# C++ Multidimensional Arrays
An array of an array, literally meaning that its a two dimensional array.

![[Screenshot 2025-06-05 at 1.17.56 PM.jpg]]

Three dimensional arrays also exist, and work the exact same way.
> [!Syntax] 🔖 Syntax: Multidimensional Array
> `float x[2][4][3]`
- To calculate the total amount  of elements in the array simply by multiplying the dimensions: $2 * 4 * 3 = 24$

**Two-Dimensional Array Initialization**:
1. The first way is the normal initialization
```cpp
int test[2][3] = {2,4,5,9,0,19};
```
2. The second method is much more preferred by developers as it allows the user to specify the items in each array
```cpp
int  test[2][3] = { {2, 4, 5}, {9, 0, 19}};
```

![[Screenshot 2025-06-05 at 1.25.51 PM.jpg]]

**Three-Dimensional Array**
1. The first method is not preferred
```cpp
int test[2][3][4] = {3, 4, 2, 3, 0, -3, 9, 11, 23, 12, 23, 
                 2, 13, 4, 56, 3, 5, 9, 3, 5, 5, 1, 4, 9};
```
2. The second way is much more preferred as it allows the user to visualize the items being stored in each array.
```cpp
int test[2][3][4] = { 
                     { {3, 4, 2, 3}, {0, -3, 9, 11}, {23, 12, 23, 2} },
                     { {13, 4, 56, 3}, {5, 9, 3, 5}, {5, 1, 4, 9} }
                 };
```

The first dimension has a value of 2, which means it holds two elements within:
```
Element 1 = { {3, 4, 2, 3}, {0, -3, 9, 11}, {23, 12, 23, 2} }
Element 2 = { {13, 4, 56, 3}, {5, 9, 3, 5}, {5, 1, 4, 9} }
```

*Example 1: Two Dimensional Array*
```cpp
// C++ Program to display all elements
// of an initialised two dimensional array

#include <iostream>
using namespace std;

int main() {
    int test[3][2] = {{2, -5},
                      {4, 0},
                      {9, 1}};

    // use of nested for loop
    // access rows of the array
    for (int i = 0; i < 3; ++i) {

        // access columns of the array
        for (int j = 0; j < 2; ++j) {
            cout << "test[" << i << "][" << j << "] = " << test[i][j] << endl;
        }
    }

    return 0;
}
/* 
test[0][0] = 2
test[0][1] = -5
test[1][0] = 4
test[1][1] = 0
test[2][0] = 9
test[2][1] = 1
*/
```

*Example 2 - Taking input for two dimensional array*
```cpp
#include <iostream>
using namespace std;

int main() {
    int numbers[2][3];

    cout << "Enter 6 numbers: " << endl;

    // Storing user input in the array - Nested Loop
    for (int i = 0; i < 2; ++i) {
        for (int j = 0; j < 3; ++j) {
            cin >> numbers[i][j];
        }
    }

    cout << "The numbers are: " << endl;

    //  Printing array elements
    for (int i = 0; i < 2; ++i) {
        for (int j = 0; j < 3; ++j) {
            cout << "numbers[" << i << "][" << j << "]: " << numbers[i][j] << endl;
        }
    }

    return 0;
}
/* 
Enter 6 numbers: 
1
2
3
4
5
6
The numbers are:
numbers[0][0]: 1
numbers[0][1]: 2
numbers[0][2]: 3
numbers[1][0]: 4
numbers[1][1]: 5
numbers[1][2]: 6
*/
```

*Example 3 - Three Dimensional Array*
```cpp
// C++ Program to Store value entered by user in
// three dimensional array and display it.

#include <iostream>
using namespace std;

int main() {
    // This array can store upto 12 elements (2x3x2)
    int test[2][3][2] = {
                            {
                                {1, 2},
                                {3, 4},
                                {5, 6}
                            }, 
                            {
                                {7, 8}, 
                                {9, 10}, 
                                {11, 12}
                            }
                        };

    // Displaying the values with proper index.
    for (int i = 0; i < 2; ++i) {
        for (int j = 0; j < 3; ++j) {
            for (int k = 0; k < 2; ++k) {
                cout << "test[" << i << "][" << j << "][" << k << "] = " << test[i][j][k] << endl;
            }
        }
    }

    return 0;
}
/* 
test[0][0][0] = 1
test[0][0][1] = 2
test[0][1][0] = 3
test[0][1][1] = 4
test[0][2][0] = 5
test[0][2][1] = 6
test[1][0][0] = 7
test[1][0][1] = 8
test[1][1][0] = 9
test[1][1][1] = 10
test[1][2][0] = 11
test[1][2][1] = 12
*/
```

---
# III - Vectors

















































---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on::[Containers library - cppreference.com](https://en.cppreference.com/w/cpp/container.html)

