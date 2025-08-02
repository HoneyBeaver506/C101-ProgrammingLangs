---
Title: "202505291314"
Topic: CLang Learning Curve
tags:
  - programming/clang
  - type/note
  - type/sketchnote
aliases: []
template_type: Note
template_version: "1.35"
Created At: Thursday, May 29th 2025, 1:14:51 pm
Modified At: Sunday, June 1st 2025, 8:57:52 pm
created: 2025-05-29T13:14
updated: 2025-06-29T16:24
---
<!--  See "Template Help" below for using properties -->

*Table of Contents*
- [[#II. If, If...else, Nested If Else|II. If, If...else, Nested If Else]]
- [[#III. If ... Else Statement|III. If ... Else Statement]]
- [[#IV. If .. Else .. Else if Statement|IV. If .. Else .. Else if Statement]]
- [[#V. C++ For Loops|V. C++ For Loops]]
- [[#VI. C++ While Loop|VI. C++ While Loop]]
- [[#VII. C++ Statements|VII. C++ Statements]]
- [[#VIII. Switch ... Case Statement|VIII. Switch ... Case Statement]]




# 202505291314 - C++ Conditional Statements
> [!Summary]
> *This section Covers:*
> - If, If else and Nested If Else
> - For Loops
> - While do & Do While
> - Break, Continue, goto statements
> - Switch Case Statement
> - Ternary Operator






# I. C++ Conditional Statements
- [[#II. If, If...else, Nested If Else|II. If, If...else, Nested If Else]]
- [[#III. If ... Else Statement|III. If ... Else Statement]]
- [[#IV. If .. Else .. Else if Statement|IV. If .. Else .. Else if Statement]]
- [[#V. C++ For Loops|V. C++ For Loops]]
- [[#VI. C++ While Loop|VI. C++ While Loop]]
- [[#VII. C++ Statements|VII. C++ Statements]]
- [[#VIII. Switch ... Case Statement|VIII. Switch ... Case Statement]]

## II. If, If...else, Nested If Else
These statements are used to run when certain conditions are true. For example, using the assignment of graces based on the marks obtained:
- If the percentage is above 90, assign A
- If the percentage is above 75, assign B
- If the percentage is above 65, Assign grade C

> [!Syntax] 🔖 Syntax:  C++
> if (condition) {
>    // Body of if statement - Runs if condition is true
> }
> 
- The parenthesis is the condition which is evaluated by the `if` statement.
	- If the condition evaluates to `true`, then the code inside the body is executed
	- if the condition evaluates to `false`, then the code inside the body is skipped.

![[Screenshot 2025-05-29 at 1.24.37 PM.jpg]]

```cpp
// Program to print positive number entered by the user
// If the user enters a negative number, it is skipped

#include <iostream>
using namespace std;

int main() {

  int number;

  cout << "Enter an integer: ";
  cin >> number;

  // checks if the number is positive
  if (number > 0) {
    cout << "You entered a positive integer: " << number << endl;
  }

  cout << "This statement is always executed.";

  return 0;
}
/* 
Enter an integer: 5
You entered a positive number: 5
This statement is always executed.
*/
```
- When the user enters the number 5, the condition is evaluated to `true` based on the condition (`number > 0` or number is greater than 0)  
- This changes when the user enters a negative number however, which evaluates the condition as `false` and the code outside of the `if` statement is executed.

## III. If ... Else Statement
![[Screenshot 2025-05-29 at 1.31.10 PM.jpg]]
- The `if .. else` statement is an optional clause that keeps the false code inside of the code block. This means that if the code block evaluates to false, then the code inside of the else statement will execute.
- This is optimal for If - else if - else statements, helping keep code inside of the condition

```cpp
// Program to check whether an integer is positive or negative
// This program considers 0 as a positive number

#include <iostream>
using namespace std;

int main() {

  int number;

  cout << "Enter an integer: ";
  cin >> number;

// Evaluates if the variable `number` is greater than 0
  if (number >= 0) {
  // if the number is 5, then the condition evaluates to true and does:
    cout << "You entered a positive integer: " << number << endl;
  }
  else {
  // If the number is -4, then the condition evaluates to false and does:
    cout << "You entered a negative integer: " << number << endl;
  }

  cout << "This line is always printed.";

  return 0;
}
```
- If the if-else statement has only one condition, you can skip the usage of curly braces. 

---
## IV. If .. Else .. Else if Statement
used to execute a block of code among two alternatives. This is just another way of saying that the code can evaluate two or more conditions at a time.
- This is restricted only if the first condition evaluates to true
*Code Example*:
``` cpp
// Program to check whether an integer is positive, negative or zero

#include <iostream>
using namespace std;

int main() {

  int number;

  cout << "Enter an integer: ";
  cin >> number;
// Condition 1
  if (number > 0) {
    cout << "You entered a positive integer: " << number << endl;
  } 
  // only runs if condition 1 is true
  else if (number < 0) {
    cout << "You entered a negative integer: " << number << endl;
  } 
  // executes only if both conditions are false
  else {
    cout << "You entered 0." << endl;
  }

  cout << "This line is always printed.";

  return 0;
}
```

*Outputs:*
```markdown
**Output 1**
Enter an integer: 1
You entered a positive integer: 1.
This line is always printed.

**Output 2**
Enter an integer: -2
You entered a negative integer: -2.
This line is always printed.

**Output 3**

Enter an integer: 0
You entered 0.
This line is always printed.
```

---
## V. C++ For Loops
Loops are used to repeat a block of code. this helps with things like writing a statement 100 times.
- Used for known numbers such as the array size and the range.
> [!Syntax]+ 🔖 Syntax: 
>  for (initialization;  condition; update ) {
> 	 // Code to Be Repeated
>  }

**Basic Structure**:
- **Initialization**: "Start at the starting line." (Where do you begin?)
	- runs once at the very start
	- Sets the counter variable, which is a regular var that constantly changes and tracks as the loop runs
- **Condition**: "Keep running as long as you haven't completed 5 laps." (When do you stop?)
	- Checked before each rep
	- If the condition is true / met, then the code inside is run, if false, the loop stops (*Analogy*: Continue as long as …)
- **Update**: "After each lap, mark it down on your tracker." (What do you do after each repetition to get closer to stopping?)
	- Runs after each repetition.
	- Changes the counter variable by either incrementing (++) or decrementing (- -)
	- Can also use (`+=  or i = i * 2`)
	- if not set, an infinite loop is created
- **Code to be repeated**: "Run one lap." (The actual action you perform repeatedly.)

*Flow control of the Loop*
- The **init** step is executed first, and only once. This step allows you to declare and initialize any loop control variables. You are not required to put a statement here, as long as a semicolon appears.
- Next, the **condition** is evaluated. If it is true, the body of the loop is executed. If it is false, the body of the loop does not execute and flow of control jumps to the next statement just after the for loop.
- After the body of the for loop executes, the flow of control jumps back up to the **increment** statement. This statement can be left blank, as long as a semicolon appears after the condition.
- The condition is now evaluated again. If it is true, the loop executes and the process repeats itself (body of loop, then increment step, and then again condition). After the condition becomes false, the for loop terminates.

*Example Code*:
```cpp
#include <iostream>

using namespace std;

int main() {
        for (int i = 1; i <= 5; ++i) {
        cout << i << " ";
    }
    return 0;
}
// 1 2 3 4 5
```
- Works with text as well. Just replace the i with the text
- The `" "` is known as a string whitespace which means it just prints a space then the next number.

*Find the sum of natural number Bases:*
```cpp
for (int i = 1; i <= num; ++i) {
        sum += i;
    }
```
- `int i = 1`: initializes the i variable
- `i <= num`: runs the loop as long as i is less than or equal to num
- `++i`: increases the i variable by 1 in each iteration

----
**For Loop "Recipe" (The three Key Parts)**
has three ingredients that are separated by semicolons and its parenthesis. 

*Ingredients:*
1. **Initilization**: Its the part that sets up the basic counter variable. It tells the loop where it beguns.
	1. **Analogy**: "Start counting from 0" or "set the first item of the process"
	2. **Example**: (`int i = 0;`) This creates the variable named I which can be any letter, then sets its initial value to 0, or the starting value of the counter. (`i` is common. Refers to index or iterator)
2. **Condition: ("Keep Going" Way)** : This sets the condition for the loop, basically as long as the condition is true, the loop will continue until false.
	1. **Analogy**: "Keep the loop going as long as the count is less then 10/ more then 20/ less than or equal to 100"
	2. **Example**: (`i < 10`) (i is less than 10) -> basically means the loop stars from zero and ends at 10. if it was (==less than or equal to==), the 10 is included, inclusively
3. **Update (The Step Forward)**: This counter changes the counter variable by increasing or decreasing it. It is how the loop progresses to the stopping point.
	1. **Analogy**: "After you do the task, increment the count one by one" or "Move on to the next" (counting)
	2. **Example**: (`i++`) - Increments the counter by 1; ==1 = i + 1==






**Ranged Based Loop:**
> [!Syntax]+ 🔖 Syntax:  C++
for (variable : collection) {}

Here, for every value in the `collection`, the for loop is executed and the value is assigned to the `variable`.
- Arrays, vectors and other storages are referred to ==collections==

*Example Code*:
```cpp
#include <iostream>

using namespace std;

int main() {
  
    int num_array[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    // Creates the variable; Counts every number one by one.  
    for (int n : num_array) {
        cout << n << " ";
    }
  
    return 0;
}
// 1 2 3 4 5 6 7 8 9 10
```

*infinite loop: If the condition is always true*
> [!Syntax]+ 🔖 Syntax: c++
// infinite for loop
for(int i = 1; i > 0; i++) { ... }


Find the sum of Natural Numbers:
- The use of while loops to continue. This is not a loop
```cpp
#include <iostream>

int main() {
    int num{}; // Declare and initialize num
    std==cout << "[+] Type a Number? " << std==endl;
    std::cin >> num; // Get input for num

    // Now, define 'n' based on 'num' (or simply use 'num' directly in the formula)
    // For clarity, let's assume 'n' is meant to be 'num' here.
    // If 'n' is a separate variable, it needs its own definition and value.
    const int n = num; // 'n' is defined and has a value from 'num'

    // Now, 'formula' can be initialized correctly
    const int formula = n * (n + 1) / 2; // Calculates sum of 1 to n (which is 1 to num)

    std==cout << "The sum of numbers from 1 to " << num << " is: " << formula << std==endl;

    if (num > 5) {
        std==cout << "Your number is greater than 5!" << std==endl;
    } else {
        std==cout << "Your number is not greater than 5!" << std==endl;
    }

    return 0;
}
```

![[C++ Conditionals 2025-06-09 16.57.36.excalidraw]]

|Loop Iteration|Initialization|Condition (i < 3)|Loop Body Executed?|Update (i++)|Value of i after update|
|:--|:--|:--|:--|:--|:--|
|Before Loop|i = 0|N/A|No|N/A|0|
|1st Iteration|N/A|0 < 3 (True)|Yes|i becomes 1|1|
|2nd Iteration|N/A|1 < 3 (True)|Yes|i becomes 2|2|
|3rd Iteration|N/A|2 < 3 (True)|Yes|i becomes 3|3|
|After 3rd|N/A|3 < 3 (False)|No (Loop ends)|N/A|3|

---
## VI. C++ While Loop
This is another loop that repeats, except instead of using a range, it just uses a condition to do so.
- Used when values are not known (Random Numbers)

> [!Syntax]+ 🔖 Syntax: C++ While Loop
> while (condition) { ... }

- If the condition inside the code evaluates to true the loop is executed as long as its true.
- The code stops executing once the condition turns false

*Example: Display Number from 1 to 5*
```cpp
// C++ Program to print numbers from 1 to 5

#include <iostream>

using namespace std;

int main() {
    int i = 1; 

    // while loop from 1 to 5
    while (i <= 5) {
        cout << i << " ";
        ++i;
    }
    
    return 0;
}
// 1 2 3 4
```
- continues until the number is less or equal to 5.


*Example 2: Sum of positive nums only*
```cpp
// program to find the sum of positive numbers
// if the user enters a negative number, the loop ends
// the negative number entered is not added to the sum

#include <iostream>
using namespace std;

int main() {
    int number;
    int sum = 0;

    // take input from the user
    cout << "Enter a number: ";
    cin >> number;

    while (number >= 0) {
        // add all positive numbers
        sum += number;

        // take input again if the number is positive
        cout << "Enter a number: ";
        cin >> number;
    }

    // display the sum
    cout << "\nThe sum is " << sum << endl;
    
    return 0;
}
/* 
Enter a number: 6
Enter a number: 12
Enter a number: 7
Enter a number: 0
Enter a number: -2

The sum is 25
*/
```
- The while loop continues until the number is negative.

**Do ... While loops**
This loop executes the code first then evaluates the condition as the bottom. This guarantees it executes as long as one time.

> [!Syntax] 🔖 Syntax: C++ Do .. While
> do { statement(s); }
> while (Condition);
> 

- The code executes at least one before the loop beins. 
- If the condition is true, the flow of control jumps back up to do, and the statements in the loops execute again. This continues until the condition is false.

![[Screenshot 2025-05-29 at 4.35.17 PM.jpg]]

*Example 1: Display numbers from 1 to 5*
```cpp
// C++ Program to print numbers from 1 to 5

#include <iostream>

using namespace std;

int main() {
    int i = 1; 

    // do...while loop from 1 to 5
    // 1 is printed and I is increased to 2 (do)
    do {
        cout << i << " ";
        ++i;
    }
    while (i <= 5);
    
    return 0;
}
// 1 2 3 4 5 
```

*Example 2: Sum of Positive Numbers*
```cpp
// program to find the sum of positive numbers
// If the user enters a negative number, the loop ends
// the negative number entered is not added to the sum

#include <iostream>
using namespace std;

int main() {
    int number = 0;
    int sum = 0;

    do {
    // Basically: sum = sum + number
        sum += number;

        // take input from the user
        cout << "Enter a number: ";
        cin >> number;
    }
    while (number >= 0);
    
    // display the sum
    cout << "\nThe sum is " << sum << endl;
    
    return 0;
}
```
- The loop continues until a negative is inputted

**Infinite While Loop**
If the condition of a loop is always true, then the loop runs infinitely until the memory is full. (dangerous cause it can lead to slowness)
> [!Syntax] 🔖 Syntax: C++ Infinite Loop
> *While Loop*
> while (true) { ... };
> *Do .. While*
> do { ... }
> while (count ==  1);



----
## VII. C++ Statements
![[Screenshot 2025-05-29 at 4.42.32 PM.jpg]]
**Break Statements**
Terminates a loop when stated.
- When the **break** statement is encountered inside a loop, the loop is immediately terminated and program control resumes at the next statement following the loop.
- It can be used to terminate a case in the **switch** statement (covered in the next chapter).

*Example 1: Breaking a  For Loop*
```cpp
// program to print the value of i

#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 5; i++) {
        // break condition     
        if (i == 3) {
            break;
        }
        cout << i << endl;
    }

return 0;
}
// 1 2
```

*Example 2: Breaking a  While Loop*
```cpp
// program to find the sum of positive numbers
// if the user enters a negative numbers, break ends the loop
// the negative number entered is not added to sum

#include <iostream>
using namespace std;

int main() {
    int number;
    int sum = 0;

    while (true) {
        // take input from the user
        cout << "Enter a number: ";
        cin >> number;

        // break condition
        if (number < 0) {
            break;
        }

        // add all positive numbers
        sum += number;
    }

    // display the sum
    cout << "The sum is " << sum << endl;

    return 0;
}
```

**C++ Continue Statement**
Is used to skip the current iteration of the loop and the control of the program goes to the next iteration.
![[Screenshot 2025-05-31 at 9.44.56 AM.jpg]]

*For Loop with Continue*: Skips the current iteration and the control flow jumps to the update expression.
```cpp
// program to print the value of i

#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 5; i++) {
        // condition to continue
        if (i == 3) {
            continue;
        }

        cout << i << endl;
    }

    return 0;
}
/* Output: 
1
2
3
4
5
*/
```
- When i is equal to 3, the continue statement skips the current iteration and starts the next iteration.
- I then becomes 4, and the continue statement continues
- Hence 4 and 5 are printed in the next two iterations.
 
- *The continue Vs break Statements*
The **continue** statement skips the remaining part of the current iteration and moves to the next iteration of the loop. This is basically used when a user wants to skip specific iterations based on a condition. It does not terminate the loop, it just transfers the execution to the next iteration. Whereas the **break** statement terminates the loop completely based on any specific condition given and stops the further execution of the loop.

*Use Cases of Continue Statement*
- **Filtering Data:** The continue statement is useful when you filter data by skipping invalid or unwanted data in a dataset.
- **Skipping Unnecessary Calculations and Invalid User Input:** By using the **continue** statement, you can avoid redundant computations when the result for certain cases is predetermined.
- **Performance optimization:** It will optimize overall performance by avoiding unnecessary processing.
- **Beneficial for Complex Loop Structure:** As a complex loop structure requires selective execution of iterations, using a continue statement would be beneficial for such cases.


**C++ GOTO Statement**
Provides an unconditional jump from the goto to a labeled statement in the same function.
- Difficult to trace back the control flow of a program, making the program hard to understand and how hard to modify
- A label is defined with an identifier followed by a colon (:)

> [!Syntax]+  Syntax:  GOTO Syntax
> goto label;
> ...
> ..
> label: statement;

- **Label**: an identifier that identifies the labeled statement.
- **Labeled Statement**: any statement that is preceded by an identifier followed by a colon (:)

![[Screenshot 2025-05-31 at 9.56.34 AM.jpg]]

*Example 1 - Goto Code Example*
```cpp
// This program calculates the average of numbers entered by the user.
// If the user enters a negative number, it ignores the number and 
// calculates the average number entered before it.

# include <iostream>
using namespace std;

int main()
{
    float num, average, sum = 0.0;
    int i, n;

    cout << "Maximum number of inputs: ";
    cin >> n;

    for(i = 1; i <= n; ++i)
    {
        cout << "Enter n" << i << ": ";
        cin >> num;
        
        if(num < 0.0)
        {
           // Control of the program move to jump:
            goto jump;
        } 
        sum += num;
    }
    
jump:
    average = sum / (i - 1);
    cout << "\nAverage = " << average;
    return 0;
}
```
"Goto Statement in Modern Programming" 
	- Allows jump to any part of program. 
	- Complex and tangled program logic. 
	- Considered harmful construct in modern programming. 
	- Replaced by break and continue statements in most C++ programs.

----
## VIII. Switch ... Case Statement
![[Screenshot 2025-05-31 at 10.04.44 AM.jpg]]
Allows us to execute a block of code among any alternatives.  This also allows a variable to be tested equally against a list of values. Each value is called a case, and the variable being switched on is checked for each case.
```txt
	switch (expression)  {
    case constant1:
        // code to be executed if 
        // expression is equal to constant1;
        break;
    case constant2:
        // code to be executed if
        // expression is equal to constant2;
        break;
        .
        .
        .
    default:
        // code to be executed if
        // expression doesn't match any constant
}
```
Expression Evaluation and Matching 
	- Expression evaluated once and compared with case labels. 
	- If match found, code executed after matching label. 
	- If no match found, code executed after default:.
 
*Rules that Apply to a switch statement:*
- The **expression** used in a **switch** statement must have an integral or enumerated type, or be of a class type in which the class has a single conversion function to an integral or enumerated type.
- You can have any number of case statements within a switch. Each case is followed by the value to be compared to and a colon.
- The **constant-expression** for a case must be the same data type as the variable in the switch, and it must be a constant or a literal.
- When the variable being switched on is equal to a case, the statements following that case will execute until a **break** statement is reached.
- When a break statement is reached, the switch terminates, and the flow of control jumps to the next line following the switch statement.
- Not every case needs to contain a break. If no break appears, the flow of control will _fall through_ to subsequent cases until a break is reached.
- A **switch** statement can have an optional **default** case, which must appear at the end of the switch. The default case can be used for performing a task when none of the cases is true. No break is needed in the default case.

*Example 1 - Switch Calculator Example*
```cpp
// Program to build a simple calculator using switch Statement
#include <iostream>
using namespace std;

int main() {
    char oper;
    float num1, num2;
    cout << "Enter an operator (+, -, *, /): ";
    cin >> oper;
    cout << "Enter two numbers: " << endl;
    cin >> num1 >> num2;

    switch (oper) {
        case '+':
            cout << num1 << " + " << num2 << " = " << num1 + num2;
            break;
        case '-':
            cout << num1 << " - " << num2 << " = " << num1 - num2;
            break;
        case '*':
            cout << num1 << " * " << num2 << " = " << num1 * num2;
            break;
        case '/':
            cout << num1 << " / " << num2 << " = " << num1 / num2;
            break;
        default:
            // operator is doesn't match any case constant (+, -, *, /)
            cout << "Error! The operator is not correct";
            break;
    }

    return 0;
}
/* 
Enter an operator (+, -, *, /): +
Enter two numbers: 
2.3
4.5
2.3 + 4.5 = 6.8
*/
```
**How This Program Works**
1. We first prompt the user to enter the desired Operator. This input is then stored in the `char` variable named `oper`.
2. We then prompt the user to enter two numbers, which are stored in the float variables num1 and num2.
3. The `switch` statement is then used to check the operator entered by the user:
    1. If the user enters `+`, addition is performed on the numbers.
    2. If the user enters `-`, subtraction is performed on the numbers.
    3. If the user enters `*`, multiplication is performed on the numbers.
    4. If the user enters `/`, division is performed on the numbers.
    5. If the user enters any other character, the default code is printed.
If the `break` statement is not used, all cases after the correct `case` are executed.

----

# IX. Conclusion
| Sr.No | Statement & Description                                                                                                                                                                                                                        |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | [if statement](https://www.tutorialspoint.com/cplusplus/cpp_if_statement.htm "C++ if statement")<br><br>An if statement consists of a boolean expression followed by one or more statements.                                                   |
| 2     | [if...else statement](https://www.tutorialspoint.com/cplusplus/cpp_if_else_statement.htm "C++ if...else statement")<br><br>An if statement can be followed by an optional else statement, which executes when the boolean expression is false. |
| 3     | [switch statement](https://www.tutorialspoint.com/cplusplus/cpp_switch_statement.htm "C++ switch statement")<br><br>A switch statement allows a variable to be tested for equality against a list of values.                                   |
| 4     | [nested if statements](https://www.tutorialspoint.com/cplusplus/cpp_nested_if.htm "C++ nested if statements")<br><br>You can use one if or else if statement inside another if or else if statement(s).                                        |
| 5     | [nested switch statements](https://www.tutorialspoint.com/cplusplus/cpp_nested_switch.htm "C++ nested switch statements")<br><br>You can use one switch statement inside another switch statement(s).                                          |











----
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on:: Self Made

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see:: [[C++ References & CheatSheets]]

