---
Title: J1 - Java Basics
Topic: Java Learning Curve
tags:
  - programming/java
  - theme/concept
  - type/note
created: 2025-06-06T14:20
updated: 2025-06-06T14:25
---

---
*Table of Contents*
- [[#Comments|Comments]]
- [[#Java Basic Syntax|Java Basic Syntax]]
	- [[#Java Basic Syntax#Java Identifiers|Java Identifiers]]
	- [[#Java Basic Syntax#Java Modifiers|Java Modifiers]]
	- [[#Java Basic Syntax#Java Variables|Java Variables]]
	- [[#Java Basic Syntax#Java Arrays|Java Arrays]]
	- [[#Java Basic Syntax#Java Enums|Java Enums]]
	- [[#Java Basic Syntax#Java Keywords|Java Keywords]]
	- [[#Java Basic Syntax#Inheritance|Inheritance]]

# Java Basics - Learning Curve
—
## Comments
Comments are used to document and describe a section of code. They also work to disable sections that you do not want to use.

**Single Line Comments** - `//`
**Multi Line Comments** - `/* */` (Basically C++)

## Java Basic Syntax

**Collection of Objects that Communicate with each other:**
- *Object*: Objects have states and behaviors.
	- *Example:* A dog has states: Color, Name, Breed as well as their behavior. An object is an instance of a class.
- *Class*: A class can be defined as a Template/Blueprint that describes behavior/state that the object of its type supports (C++/Python)
- *Methods:* A method is basically a behavior. A class can contain many methods/functions. It is in methods where the logics are written, data is manipulated and all the actions are executed.
- *Instance Variables:* Each object has its unique set of instance variables. An object’s state is created by the values assigned to these instance variables.

```bash
# Basic Program Execution
javac firstProgram.java
java firstProgram
```

- **Case Sensitivity** − Java is case sensitive, which means identifier **Hello** and **hello** would have different meaning in Java.
    
- **Class Names** − For all class names the first letter should be in Upper Case. If several words are used to form a name of the class, each inner word's first letter should be in Upper Case.
    
    **Example** − _class MyFirstJavaClass_
    
- **Method Names** − All method names should start with a Lower Case letter. If several words are used to form the name of the method, then each inner word's first letter should be in Upper Case.
    
    **Example** − _public void myMethodName()_
    
- **Program File Name** − Name of the program file should exactly match the class name.
    
    When saving the file, you should save it using the class name (Remember Java is case sensitive) and append '.java' to the end of the name (if the file name and the class name do not match, your program will not compile).
    
    But please make a note that in case you do not have a public class present in the file then file name can be different than class name. It is also not mandatory to have a public class in the file.
    
    **Example** − Assume 'MyFirstJavaProgram' is the class name. Then the file should be saved as _'MyFirstJavaProgram.java'_
    
- **public static void main(String args[])** − Java program processing starts from the main() method which is mandatory part of every Java Program.

### Java Identifiers
All java components require names. Names used for classes, variables, and methods are called **Identifiers**.

In java, several rules should be followed:
- All identifiers should begin with a letter (A to Z or a to z), currency character ($) or an underscore (_).
- After the first character, identifiers can have any combination of characters.
- A keyword cannot be used as an identifier.
- Most importantly, identifiers are case sensitive.
- Examples of legal identifiers: age, $salary, _value, __1_value.
- Examples of illegal identifiers: 123abc, -salary.

### Java Modifiers
It is possible to modify classes, methods, et., by using modifiers.
There are two types of modifiers:
- **Access Modifiers** - Default, Public, Protected, & Private
- **No-Access Modifiers** - Final, Abstract, & strictfp

### Java Variables
There are three types of variables in Java:
- Local Variables
- Class Variables (Static)
- Instance Variables (Non-Static)

### Java Arrays
Arrays are objects that store multiple variables of the same type. However, an array itself is an object on the heap. These need to be declared, constructed, and initialized.

### Java Enums
Enums restrict variables to have one of a few predefined values. The values in this enumerated lists are called enums.

With the use of enums it is possible to reduce the number of bugs in your code.

*Example*:  If we consider an app for a Juice Shop, it would be possible to restrict glass size to small, medium or large. This would make sure customers are allowed to chose.

### Java Keywords
|Sr.No|Reserved Words & Description|
|---|---|
|1|[abstract](https://www.tutorialspoint.com/java/java_abstraction.htm)<br><br>As per dictionary, **abstraction** is the quality of dealing with ideas rather than events.|
|2|[assert](https://www.tutorialspoint.com/java/assert_keyword_in_java.htm)<br><br>**assert** keyword is used in Java to define assertion. An assertion is a statement in Java which ensures the correctness of any assumptions which have been done in the program.|
|3|[boolean](https://www.tutorialspoint.com/java/boolean_keyword_in_java.htm)<br><br>boolean datatype is one of the eight primitive datatype supported by Java. It provides means to create boolean type variables which can accept a boolean value as true or false.|
|4|[break](https://www.tutorialspoint.com/java/java_break_statement.htm)<br><br>The **break** statement in Java programming language has the following two usages −<br><br>- When the **break** statement is encountered inside a loop, the loop is immediately terminated and the program control resumes at the next statement following the loop.<br>    <br>- It can be used to terminate a case in the **switch** statement.|
|5|[byte](https://www.tutorialspoint.com/java/byte_keyword_in_java.htm)<br><br>byte datatype is one of the eight primitive datatype supported by Java. It provides means to create byte type variables which can accept a byte value.|
|6|[case](https://www.tutorialspoint.com/java/case_keyword_in_java.htm)<br><br>**case** keyword is part of **switch** statement which allows a variable to be tested for equality against a list of values.|
|7|[catch](https://www.tutorialspoint.com/java/catch_keyword_in_java.htm)<br><br>An exception (or exceptional event) is a problem that arises during the execution of a program.|
|8|[char](https://www.tutorialspoint.com/java/char_keyword_in_java.htm)<br><br>char datatype is one of the eight primitive datatype supported by Java.|
|9|[class](https://www.tutorialspoint.com/java/java_object_classes.htm)<br><br>Java is an Object-Oriented Language. As a language that has the Object-Oriented feature.|
|10|[const](https://www.tutorialspoint.com/java/final_keyword_in_java.htm)<br><br>**final** keyword is used to define constant value or final methods/classes in Java.|
|11|[continue](https://www.tutorialspoint.com/java/java_continue_statement.htm)<br><br>The **continue** keyword can be used in any of the loop control structures.|
|12|[default](https://www.tutorialspoint.com/java/default_keyword_in_java.htm)<br><br>**default** keyword is part of **switch** statement which allows a variable to be tested for equality against a list of values.|
|13|[do](https://www.tutorialspoint.com/java/java_do_while_loop.htm)<br><br>A **do...while** loop is similar to a while loop, except that a do...while loop is guaranteed to execute at least one time.|
|14|[double](https://www.tutorialspoint.com/java/double_keyword_in_java.htm)<br><br>double datatype is one of the eight primitive datatype supported by Java.|
|15|[if](https://www.tutorialspoint.com/java/if_else_statement_in_java.htm)<br><br>An **if** statement can be followed by an optional **else** statement, which executes when the Boolean expression is false.|
|16|[enum](https://www.tutorialspoint.com/java/lang/java_lang_enum.htm)<br><br>The **Java Enum** class is the common base class of all Java language enumeration types.|
|17|[extends](https://www.tutorialspoint.com/java/extends_keyword_in_java.htm)<br><br>**extends** is the keyword used to inherit the properties of a class. Following is the syntax of extends keyword.|
|18|[final](https://www.tutorialspoint.com/java/final_keyword_in_java.htm)<br><br>**final** keyword is used to define constant value or final methods/classes in Java.|
|19|[finally](https://www.tutorialspoint.com/java/finally_keyword_in_java.htm)<br><br>**finally** keyword is used to define a finally block. The finally block follows a try block or a catch block. A finally block of code always executes, irrespective of occurrence of an Exception.|
|20|[float](https://www.tutorialspoint.com/java/float_keyword_in_java.htm)<br><br>float datatype is one of the eight primitive datatype supported by Java. It provides means to create float type variables which can accept a float value.|
|21|[for](https://www.tutorialspoint.com/java/java_for_loop.htm)<br><br>A **for** loop is a repetition control structure that allows you to efficiently write a loop that needs to be executed a specific number of times.|
|22|[goto](https://www.tutorialspoint.com/java/goto_keyword_in_java.htm)<br><br>goto statement is not supported by Java currrenly. It is kept as a reserved keyword for future. As an alternative, Java supports labels with break and continue statement.|
|23|[if](https://www.tutorialspoint.com/java/if_statement_in_java.htm)<br><br>An **if** statement consists of a Boolean expression followed by one or more statements.|
|24|[implements](https://www.tutorialspoint.com/java/implements_keyword_in_java.htm)<br><br>Generally, the **implements** keyword is used with classes to inherit the properties of an interface.|
|25|[import](https://www.tutorialspoint.com/java/import_keyword_in_java.htm)<br><br>**import** keyboard is used in context of packages.|
|26|[instanceof](https://www.tutorialspoint.com/java/instanceof_keyword_in_java.htm)<br><br>**instanceof** keyword is an operator which is used only for object reference variables.|
|27|[int](https://www.tutorialspoint.com/java/int_keyword_in_java.htm)<br><br>int datatype is one of the eight primitive datatype supported by Java.|
|28|[interface](https://www.tutorialspoint.com/java/java_interfaces.htm)<br><br>An interface is a reference type in Java. It is similar to class. It is a collection of abstract methods.|
|29|[long](https://www.tutorialspoint.com/java/long_keyword_in_java.htm)<br><br>long datatype is one of the eight primitive datatype supported by Java.|
|30|native|
|31|new|
|32|[package](https://www.tutorialspoint.com/java/java_packages.htm)<br><br>Packages are used in Java in order to prevent naming conflicts, to control access, to make searching/locating and usage of classes, interfaces, enumerations and annotations easier, etc.|
|33|[private](https://www.tutorialspoint.com/java/private_keyword_in_java.htm)<br><br>Methods, variables, and constructors that are declared private can only be accessed within the declared class itself.|
|34|[protected](https://www.tutorialspoint.com/java/protected_keyword_in_java.htm)<br><br>The protected access modifier cannot be applied to class and interfaces.|
|35|[public](https://www.tutorialspoint.com/java/public_keyword_in_java.htm)<br><br>A class, method, constructor, interface, etc. declared public can be accessed from any other class.|
|36|return|
|37|[short](https://www.tutorialspoint.com/java/java_basic_datatypes.htm)<br><br>By assigning different data types to variables, you can store integers, decimals, or characters in these variables.|
|38|[static](https://www.tutorialspoint.com/java/static_keyword_in_java.htm)<br><br>The **static** keyword is used to create variables that will exist independently of any instances created for the class.|
|39|strictfp|
|40|[super](https://www.tutorialspoint.com/java/super_keyword_in_java.htm)<br><br>The **super** keyword is similar to **this** keyword.|
|41|[switch](https://www.tutorialspoint.com/java/switch_statement_in_java.htm)<br><br>A **switch** statement allows a variable to be tested for equality against a list of values.|
|42|synchronized|
|43|[this](https://www.tutorialspoint.com/java/this_statement_in_java.htm)<br><br>**this** keyword is a very important keyword to identify an object. Following are the usage of this keyword.|
|44|[throw](https://www.tutorialspoint.com/java/throw_keyword_in_java.htm)<br><br>If a method does not handle a checked exception, the method must declare it using the **throws** keyword.|
|45|[transient](https://www.tutorialspoint.com/java/transient_keyword_in_java.htm)<br><br>Serialization is a concept using which we can write the state of an object into a byte stream so that we can transfer it over the network (using technologies like JPA and RMI).|
|46|[try](https://www.tutorialspoint.com/java/catch_keyword_in_java.htm)<br><br>A method catches an exception using a combination of the **try** and **catch** keywords.|
|47|void|
|48|volatile|
|49|[while](https://www.tutorialspoint.com/java/java_while_loop.htm)<br><br>A **while** loop statement in Java programming language repeatedly executes a target statement as long as a given condition is true.|


### Inheritance 
Classes can be derived from classes. Basically, if you need to create a new class and here is already a new class that has some code you require, then that is possible to derive your new class from the already existing code.

*Java inheritance* allows you to reuse fields and methods of an existing class without having to rewrite the code in a new class. In this existing class, the original is called a **Superclass** and the second is called a **Subclass**


----

---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on::  Self Made

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see:: [[J2 - Java Variables]]
- see:: [[J3 - Java Input & Output]]
- see:: [[JavaCheatSheet.pdf]]
- see:: [[Java Index]]

---
**Tasks**
<!-- What remains to be done with this note? --> 
- Understanding the Basics is a fundamental part of understanding the core concepts of a language. The terms may be confusing but its easy to understand.

**Questions**
<!-- What remains for you to consider? --> 
- question::What is an Interface? What is the Analogy?

---
**Template Help**
<!-- Links to external help pages on GitHub. -->
- [Basic Template Structure](https://github.com/groepl/Obsidian-Templates#basic-template-structure)
- [How to Use Links](https://github.com/groepl/Obsidian-Templates#how-to-use-links)
- [How to Use Tags](https://github.com/groepl/Obsidian-Templates#how-to-use-tags)
- [How to Search Notes](https://github.com/groepl/Obsidian-Templates#how-to-search-notes)
- [Plugins Needed](https://github.com/groepl/Obsidian-Templates#obsidian-plugins-needed)
- [Find Latest Updates](https://github.com/groepl/Obsidian-Templates)






