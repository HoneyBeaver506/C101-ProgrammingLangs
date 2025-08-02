
## Practice Problems

### Basic Level (Beginner)

#### Problem 1: Positive, Negative, or Zero

**Task:** Write a Java program that takes an integer as input and prints whether it is positive, negative, or zero using `if-else if-else` statements. **Requirements:**
- Accept integer input from the user.
- Print "Positive" if the number is greater than 0.
- Print "Negative" if the number is less than 0.
- Print "Zero" if the number is equal to 0. 
**Starter Code:**
```java
import java.util.Scanner;

public class NumberChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter an integer: ");
        int number = scanner.nextInt();

        // Your code here
        
        scanner.close();
    }
}
```



#### Problem 2: Even or Odd

**Task:** Write a Java program that determines if a given integer is even or odd using an `if-else` statement. **Requirements:*
- Accept integer input from the user.
- Print "Even" if the number is even.
- Print "Odd" if the number is odd.

**Starter Code:**
```java
import java.util.Scanner;

public class EvenOddChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter an integer: ");
        int number = scanner.nextInt();

        // Your code here

        scanner.close();
    }
}
```

# Intermediate Level Problems
#### Problem 1: Simple Calculator
**Task:** Build a basic calculator that performs addition, subtraction, multiplication, or division based on user input. **Requirements:**
- Prompt the user to enter two numbers.
- Prompt the user to enter an operator (+, -, *, /).
- Use `if-else if-else` to perform the chosen operation.
- Handle division by zero.
- Print the result. **Hints:**
- You'll need to read both `double` for numbers and `String` for the operator.
- Use `equals()` method to compare strings for the operator.

#### Problem 2: Discount Calculator
**Task:** Implement a discount system based on the total purchase amount. **Requirements:**
- Ask the user for their total purchase amount.
- Apply discounts:
    - If amount >= $1000, 20% discount.
    - If amount >= $500, 10% discount.
    - If amount >= $100, 5% discount.
    - Otherwise, no discount.
- Print the original amount, discount percentage, and final amount. **Hints:**
- Use `if-else if-else` and ensure the order of conditions is correct (largest discount range first).


#### Problem 3: Login System with Attempts
**Task:** Simulate a simple login system. The user has 3 attempts to enter the correct username and password. **Requirements:**
- Define a correct `username` ("admin") and `password` ("password123").
- Use a `for` loop for attempts (up to 3).
- Inside the loop, prompt for username and password.
- Use an `if` statement to check credentials.
- If correct, print "Login successful!" and `break` the loop.
- If incorrect, print "Incorrect username or password. Attempts left: X".
- If all attempts fail, print "Account locked. Please contact support." 


## Advanced Practice Problems
#### Problem 1: Grade Calculator with Input Validation

**Task:** Create a robust grade calculator that handles invalid inputs. 
**Requirements:**
- Prompt the user to enter a numeric score (0-100).
- Use `if-else if-else` to assign a letter grade (A, B, C, D, F).
    - A: 90-100
    - B: 80-89
    - C: 70-79
    - D: 60-69
    - F: 0-59
- **Input Validation:** Use `if` statements to check if the input is within the valid range (0-100). If not, print an error message and _do not_ assign a grade.
- Handle non-numeric input gracefully (e.g., using `try-catch` with `InputMismatchException`). **Constraints:** Score must be between 0 and 100, inclusive. **Expected Complexity:** O(1) for grading, O(number of invalid attempts) for input.

#### Problem 2: Nested Conditional Logic for Event Eligibility
**Task:** Determine if a person is eligible for a special event based on age and membership status. **Requirements:**
- Ask for age and whether they are a "member" (true/false).
- Eligibility rules:
    - If age >= 18 AND is a member: "Eligible for Special Event!"
    - If age < 18 AND is a member: "Eligible for Junior Event."
    - If age >= 18 AND is NOT a member: "Eligible for Regular Event."
    - If age < 18 AND is NOT a member: "Not eligible for any event yet."
- Use nested `if` statements or a combination of `if` and logical operators.


#### Problem 3: Complex State Machine (Simplified)
**Task:** Simulate a simplified traffic light system. Based on the current light color and a pedestrian crossing request, determine the next action. 
**Requirements:**
- Current light can be "red", "yellow", or "green".
- Pedestrian request can be `true` or `false`.
- Logic:
    - If current light is "red":
        - If pedestrian request is true: "Pedestrians cross, light stays RED."
        - If pedestrian request is false: "Vehicles wait, light stays RED."
            
    - If current light is "yellow":
        - "Prepare to stop, light will turn RED."
            
    - If current light is "green":
        - If pedestrian request is true: "Vehicles stop, light turns YELLOW, then RED for pedestrians."
        - If pedestrian request is false: "Vehicles proceed, light stays GREEN."
- Use `if-else if-else` with nested `if` statements.



---
## AI Help
```
# Brief Learning Help Prompt

I'm working on: [DESCRIBE YOUR PROBLEM]

**Please help me learn by:**

1. **Explaining the core concept** - What programming principle is involved here?
2. **Giving me one key tip** - What's the most important insight for solving this type of problem?
3. **Outlining the approach** - What are the logical steps I should think through (don't give me code)?

**Important:** Don't show me the actual solution or write any code for me. I want to figure it out myself with your guidance.
```
