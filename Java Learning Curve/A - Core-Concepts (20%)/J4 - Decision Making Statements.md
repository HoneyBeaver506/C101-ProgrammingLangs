---
Title: std::map C++ Standard Library
Topic: CPP Learning Curve
aliases: 
tags:
  - type/sketchnote
  - type/note
  - programming/java
  - programming/cpp
lead: +++ Lead paragraph goes here +++
created: <% tp.file.creation_date("YYYY-MM-DD HH:mm") %>
modified: 2025-06-13, 15:21
updated: 2025-06-27T08:31
---
*Table of Contents*
- [[#If & If else statements|If & If else statements]]
- [[#Ladder if Else|Ladder if Else]]
- [[#🎯 Concept|🎯 Concept]]
- [[#🚀 Why & When to Use|🚀 Why & When to Use]]
	- [[#🚀 Why & When to Use#|]]
- [[#✍️ Syntax & Key Operations|✍️ Syntax & Key Operations]]


# Decision Making Statements

| Statement                                 | Description                                                                                                                                                                                                                    |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **If Statement**                          | Consists of boolean expression followed by one or more statements                                                                                                                                                              |
| **If … Else Statements**                  | Followed by an optional else statement, which executes when the boolean expression is false                                                                                                                                    |
| **Nested If Else**                        | Can use one if or else if statement inside of another statement                                                                                                                                                                |
| **Switch Statement**                      | Allows a variable to be tested for equality against a list of values                                                                                                                                                           |
| **?:**                                    | Conditional Operator. Used to replace if Else statements. *Syntax*: `exp1 ? exp2 : exp3`                                                                                                                                       |
| Conditionals for **Conditional Operator** | - If the value of exp1 is true, then the value of Exp2 will be the value of the whole expression.<br>    <br>- If the value of exp1 is false, then Exp3 is evaluated and its value becomes the value of the entire expression. |

## If & If else statements
[[J3 - Java Input & Output]] - Comparison Operators

The `if` statement is the simplest form of decision-making. It runs a block of code only if a specific condition is true.
	**Analogy**: If its raining, Use an Umbrella
**SYNTAX:**
```txt
if(Boolean_expression[True or False]) { 
// Executes when the Boolean expression is true 
}
```

The `else` statement provides an alternative path. It runs a block of code if the `if` condition is false. It always follows an `if` statement.
- **Analogy**: If it's raining, take an umbrella; **else** (otherwise), leave it at home.
```txt
if (condition) { 
// Code to run if the condition is true 
} else { 
// Code to run if the condition is false 
}
```


## Ladder if Else
Literally an if else decision maker followed by another while respecting the code indentations.

- An if can have zero or one else's and it must come after any else if's.
- An if can have zero to many else if's and they must come before the else.
- Once an else if succeeds, none of the remaining else if's or else's will be tested.

—
# Switch Case
![[J4 - Decision Making Statements 2025-06-26 10.44.36.excalidraw]]
## 🎯 Concept
1. What is it _at its core_?
Allows a variable to be tested for equality against a list of values and cases. 
2. How do you declare it?
```txt
switch(expression) { 
case value : 
// Statements 
break; // optional 
case value : 
// Statements 
break; // optional 
// You can have any number of case statements. 
default : // Optional 
// Statements }
```
3. Focus on the most common operations you'll use. ("What's the most basic way to do X?")
- **Case Labels**: Associated with a specific value to be compared to the expression
- **Break Statement**: Prevents a fall through, breaking a case whenever it needs to be skipped.
	- Happens naturally in languages like C & C++
- **Default Case**: Provides a way to handle cases when other case matches the value
- `if-else` statements often chain and fil the code with more lines.


## 🚀 Why & When to Use

### 
**Why use it?** What are its advantages? 
- Can be used when using multiple `if-else` statements, shortening the code and making it cleaner
- Helps test a condition using different cases
• Variables in a switch can be integers, convertable integers, strings, and enums.
• Multiple case statements can be included within a switch.
• Case value must match the variable in the switch and must be a constant or literal.
• If the variable equals a case, subsequent statements execute until a break statement is reached.
• The switch terminates when a break is reached, reversing control flow to the next line.
• An optional default case can be included at the end of the switch for tasks where none of the cases are true.
**When to use it?** Provide 2-3 real-world scenarios. 
- Handling multiple if-else chains
- Helpful with things that require multiple inputs like grades and such
- Helpful when needing to keep code well structured and formatted

## ✍️ Syntax & Key Operations

```java
public static void main(String argd[]){
	char grade = 'C';

switch(grade) {
case 'A':
	System.out.println("Excellent);
	break;
case 'B':
	System.out.println("Well Done");
	break
default:
	System.out.println("Invalid Grade");
}
}
```

---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on:: Programmiz - If - Else Statements

```cardlink
url: https://www.tutorialspoint.com/java/if_else_statement_in_java.htm
title: "If-Else Statement in Java"
description: "If-Else Statement in Java - Learn how to use if-else statements in Java to control the flow of your program. Understand syntax, examples, and best practices."
host: www.tutorialspoint.com
favicon: https://www.tutorialspoint.com/images/favicon.ico
image: https://www.tutorialspoint.com/images/tp_logo_436.png
```


---
**Tasks**
<!-- What remains to be done with this note? --> 
- Try the Problems offered by Programmiz and Tutorial Sploit. Once you understand the concept, add it to your project.

**Questions**
<!-- What remains for you to consider? --> 
- question:: ☁️ What do you think of my Documentation so far? What should I upgrade? ☁️

---
**Template Help**
<!-- Links to external help pages on GitHub. -->
- [Basic Template Structure](https://github.com/groepl/Obsidian-Templates#basic-template-structure)
- [How to Use Links](https://github.com/groepl/Obsidian-Templates#how-to-use-links)
- [How to Use Tags](https://github.com/groepl/Obsidian-Templates#how-to-use-tags)
- [How to Search Notes](https://github.com/groepl/Obsidian-Templates#how-to-search-notes)
- [Plugins Needed](https://github.com/groepl/Obsidian-Templates#obsidian-plugins-needed)
- [Find Latest Updates](https://github.com/groepl/Obsidian-Templates)<!--  See "Template Help" below for using properties -->

# J4 - Decision Making Statements
<!--  Clear and descriptive title -->

<!-- My sketchnote if available -->
```dataviewjs 
dv.paragraph(dv.current().visual);
```
<small>_Zoom: [[]] | Edit: [[]]_</small>

<!--  Most essential idea from "lead"-key  in properties section -->

> [!Summary]
> `= this.lead`

**Details**
<!-- Main content in body of my note  -->
- 

**Supporting Content**
<!-- Supporting content in tail of my note  -->
- 

---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on::

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see:: 

**Terms**
<!-- Links to definition pages. -->
- 

**Target**
<!-- Link to project note or externaly published content. -->
- used_in::

---
**Tasks**
<!-- What remains to be done with this note? --> 
- 

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