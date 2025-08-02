---
Title: J3 - Java Input & Output
Topic: Java Learning Curve
tags:
  - programming/java
  - theme/concept
  - type/note
created: 2025-06-06T14:20
updated: 2025-06-06T14:25
---

*Table of Contents*
- [[#User Input in Java|User Input in Java]]
- [[#Java Operators|Java Operators]]
	- [[#Java Operators#Java Arithmetic Operators|Java Arithmetic Operators]]
	- [[#Java Operators#Java Assignment Operators|Java Assignment Operators]]
	- [[#Java Operators#Java Relational Operators|Java Relational Operators]]
	- [[#Java Operators#Java Logical Operators|Java Logical Operators]]
	- [[#Java Operators#Java Bitwise Operators|Java Bitwise Operators]]
	- [[#Java Operators#Java Operator Precedence and Associativity|Java Operator Precedence and Associativity]]

## User Input in Java
The `Scanner` class needs to be used. This is a bult in class of `java.util` package. Provides many built in methods to take different user inputs.

**Steps to se the Scanner Class**
1. Import Scanner Class `import java.uti.Scanner`
2. Create Scanner Class Object `Scanner obj - new Scanner(System.in);`
3. Take User Input `int age = obj.nextInt();`
	1. Takes input for an interger 

**Basic Methods for Scanner Class**
- **`String next()`**: This method finds and returns the next complete token from this scanner.
- **`BigDecimal nextBigDecimal()`**: This method scans the next token of the input as a BigDecimal.
- **`BigInteger nextBigInteger()`**: This method scans the next token of the input as a BigInteger.
- **`boolean nextBoolean()`**: This method scans the next token of the input into a boolean value and returns that value.
- **`byte nextByte()`**: This method scans the next token of the input as a byte.
- **`double nextDouble()`**: This method scans the next token of the input as a double.
- **`float nextFloat()`**: This method scans the next token of the input as a float.
- **`int nextInt()`**: This method scans the next token of the input as an int.
- **`String nextLine()`**: This method advances this scanner past the current line and returns the input that was skipped.
- **`long nextLong()`**: This method scans the next token of the input as a long.
- **`short nextShort()`**: This method scans the next token of the input as a short.


> [!important]+
> `scanner.nextLine()` after `scanner.nextInt()` is crucial when needing to read the number and line close to each other.  If it does not consume the `scanner.nextLine` followed by the subsequent `nextLine()` calls, it could lead to unexpected behavior.

---
## Java Operators
### Java Arithmetic Operators
Mathematical Expressions - Same as C++
1. `+` (Addition) - Adds values on either side of OP 
2. `-` (Subtraction) - Subtracts right-hand operand from left hand operand
3. `*` (Multiplication) - Multiplies values on either side of the operator
4. `/` (Division) - Divides left hand and right side of operand
5. `%` (Modulus) - Divides left hand operand by right hand operand. (Remainder)
6. `++` (Increments) - Increases the value of the operand by 1
7. `--` (Decrement) - Decreases the value of the operand by 1

### Java Assignment Operators
1. “=” (Simple Assignment Operator) - Simple assignment operator. Assigns values from right side operands to left side operand.
2. `+=` (Add and assing) - Add AND assignment operator. It adds right operand to the left operand and assign the result to left operand.
3. `-=` (Subtract AND Assign)
4. `*=` (Multiply AND Assign)
5. `/=` (Divide AND Assign) 
6. `%=` (Divide/Remainder AND Assignment)
7. `<<=` (Left Shift AND Assignment)
8. =>> (Right Shift AND Assignment)
9. &= (Bitwise AND Assignment)
10. ^= (Bitwise Exclusive AND Assignment)
   11. |= (Bitwise Inclusive AND Assignment)

### Java Relational Operators
Used to compare two values. These operators return a boolean value. True if the condition is met and False otherwise. 

1. == (Equal to)
2. != (Not Equal To)
3. > (Greater Than)
4. < (Less Than)
5. > = (Greater than or Equal to)
6. <= (Less than or Equal to)

### Java Logical Operators
Used to perform logical operations on boolean values. Used in decision making statements

1. && (Logical AND) - Returns True if both operands are true, otherwise it returns false
2. || (Logical OR) - Returns true if at least one of the operands are true
3. ! (Logical NOT) - Reverses the logical state of the operand

### Java Bitwise Operators
Used to perform operations at the binary (bit) level. These operators work on individual bits of numbers. Used in low level programming, encryption and performance optimization.
```java
a = 0011 1100 
b = 0000 1101 
a&b = 0000 1100 
a|b = 0011 1101 
a^b = 0011 0001 
~a = 1100 0011
```

1. & (Bitwise AND) -  Binary AND operator copies a bit of the result if it exists in both operands
2. | (Bitwise OR)  - Binary OR operator copies a bit if it exists in either operand
3. ^ (Bitwise XOR) - Copies the bit if it is set in one operand but not both
4. ~ (Bitwise Compliment)
5. << (Left Shift) - Binary Left Shift operator. The left operand value is moved left by the number of its bits specified by the right operand
6. > > (Zero Fill Right Shift) - Shift right zero fill operator. The left operands value is moved right by the number of bits specified by the right operand and shifted values are filled up with zeros.


### Java Operator Precedence and Associativity
• Operator precedence determines which part of an expression is evaluated first. 
• Java follows a predefined order for solving expressions with multiple operators. 
• Associativity determines the direction of execution of operators of the same precedence level. 
• Certain operators have higher precedence than others, like multiplication or addition. 
• Example: x = 7 + 3 * 2 is assigned 13, not 20 because operator * has higher precedence than +.
—
- **Left to Right Associativity:** Operators like `+`, `-`, `*`, `/`, `&&`, and `||` are evaluated from left to right.
- **Right to Left Associativity:** Operators like are evaluated from right to left.

![[Screenshot 2025-06-13 at 3.16.24 PM.jpg]]
- Highest Precedence appear at the top of the table
- Lowest Precedence appears at the low of the table


----

---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on:: Programmiz - Java Input and Output

```cardlink
url: https://www.programiz.com/java-programming/basic-input-output
title: "Java Basic Input and Output"
description: "In this tutorial, you will learn simple ways to display output to users and take input from users in Java. We will use the print() method to display output and the Scanner class to take input."
host: www.programiz.com
```



**Terms**
<!-- Links to definition pages. -->
- [[D2 - Terms & Definitions]]

---
**Tasks**
<!-- What remains to be done with this note? --> 
-  You may have noticed how my notes change from sloppier to cleaner and organized. I will keep it this way as it shows how my notes evolved over time.

**Questions**
<!-- What remains for you to consider? --> 
- question::

---
**Template Help**
<!-- Links to external help pages on GitHub. -->
- [Basic Template Structure](https://github.com/groepl/Obsidian-Templates#basic-template-structure)
- [How to Use Links](https://github.com/groepl/Obsidian-Templates#how-to-use-links)
- [How to Use Tags](https://github.com/groepl/Obsidian-Templates#how-to-use-tags)
- [How to Search Notes](https://github.com/groepl/Obsidian-Templates#how-to-search-notes)
- [Plugins Needed](https://github.com/groepl/Obsidian-Templates#obsidian-plugins-needed)
- [Find Latest Updates](https://github.com/groepl/Obsidian-Templates)