---
Title: J2 - Java Variables
Topic: Java Learning Curve
tags:
  - programming/java
  - theme/concept
  - type/note
created: 2025-06-06T14:33
updated: 2025-06-29T00:28
---

*Table of Contents*:
- [[#Java Variables|Java Variables]]
	- [[#Java Variables#Variable Declaration & Initialization|Variable Declaration & Initialization]]
- [[#Java Data Types|Java Data Types]]
	- [[#Java Data Types#Unicode System|Unicode System]]
- [[#Back Matter|Back Matter]]



## Java Variables
- [[#Variable Declaration & Initialization|Variable Declaration & Initialization]]

A variable provides us with named storage that our programs can manipulate. Each variable has a specific type which determines the size and layout of the variables memory. 

### Variable Declaration & Initialization
Variables must be declared before used.
- Declared by specifying data type
- Use the (=) assignment operator followed by the value
- Every variable must end with (;)

> [!Syntax] Syntax: Variable init
> ```java
> data_type variable [=value], variable [=value];
> ```

```java
// Example Variables
int a,b,c;
int a = 10, b = 10;
byte B = 22;
double pi = 3.14159;
char a = 'a';
```

**Java Variable Types**
- Local Variables
	- Declared in methods, constructors, or blocks (only allowed in specific areas)
	- *Access Modifiers* cannot be used on local vars
	- Visible only within declared method
	- Implemented at stack level internally
	- No default value
	- Organization: Makes sure tasks do not get mixed up
	- Memory Management: All local vars within are erased once the method is done
	- Encapsulation: “Bundling data with the methods that operate on the data”. Keeps data confined to where it is needed.

```cpp
public class Test {
	public void pupAge() {
		int age = 0;
		age = age + 7;
		System.out.println("Puppy's Age is:" + age);
	}
public static void main(String args[]) {
	Test test = new Test();
	test.pupAge();
}
}
```

*Excalidraw Diagram - Local Variables*
![[J2 - Java Variables 2025-06-11 11.48.26.excalidraw]]

—

- Instance Variables
	• Instance variables are declared in a class but outside a method, constructor, or block.  
	• They are created when an object is created with the keyword 'new' and destroyed when the object is destroyed.  
	• They hold values that must be referenced by multiple methods, constructors, or blocks.  
	• They can be declared in class level before or after use.  
	• Access modifiers can be given for instance variables.  
	• Variables are visible for all methods, constructors, and blocks in the class.  
	• Default values are 0, false, or null for numbers, Booleans, and object references.  
	• They can be accessed directly by calling the variable name inside the class.

```java
public class Employee {
	public String name; // Instance Variable
	public double salary; // Instance var 2

// The name variable is assigned to a constructor
public Employee (String empName) {
	name = empName
}

// The salary variable is assigned to a constructor
public void setSalary(double empSal) {
	salary = empSal

// Method 1: Prints Employee Details
public void printEmp() { 
System.out.println("name : " + name ); System.out.println("salary :" + salary); 
}


  
public static void main(String args[]) { 
Employee empOne = new Employee("Ransika"); empOne.setSalary(1000); 
empOne.printEmp(); 
} 
}

}

```

**How Instance Variables are Different from Local Variables**

|Feature|Instance Variable|Local Variable|
|:--|:--|:--|
|**Declaration**|Inside a class, but outside any method or constructor.|Inside a method, constructor, or a block of code.|
|**Existence**|Created when an object is created, destroyed when the object is destroyed. Each object has its own copy.|Created when the method/block is entered, destroyed when the method/block exits.|
|**Initialization**|If not explicitly initialized, they get default values (e.g., `0` for numbers, `null` for objects, `false` for booleans).|Must be explicitly initialized before use; no default values.|
|**Scope**|Accessible by all methods within the class. Can be accessed from outside the class depending on its access modifier.|Accessible only within the method or block where it is declared.|
- *Public*: Accessible from anywhere in the program. 
- *Private*: Accessible only within the class where it is declared

Java will automatically assign default values:
1. *Numeric Types* - Int, double, float, etc. (0 or 0.0)
2. *Boolean* Type:  false
3. *Reference Type*: String or Null

**How to use Instance Vars**
1. Declare a class
	• Defines the properties of each Employee object.  
	• Initial code defines the Employee class.  
	• Declares 'name' and'salary' instance variables.  
	• Ensures all Employee objects have a name and salary.  
	• Objects are declared outside any method.

```java
public class Employee { 
public String name; // Declares the 'name' instance variable private double salary; // Declares the 'salary' instance variable // ... rest of the class }
```

2. Define the constructor
	- Used when creating a new Employee object. 
	- Allows initial values to its instance variables.
	- new object is created using the `new` keyword.
```java
public Employee (String empName) { 
name = empName; // Assigns the value passed into the constructor to the 'name' instance variable }
```


3. Define the setSalary Method (`set`)
	• Salary is private and cannot be changed outside the Employee class.  
	• The setSalary method is included in the code.  
	• The method assigns the value passed into the method to the'salary' instance variable.  
	• This ensures a controlled way to set the salary for an Employee object.
	```java
	public void setSalary(double empSal) { 
	salary = empSal; // Assigns the value passed into the method to the 'salary' instance variable }
```

4. Define `printEmp`Method  (`print`)
	• Allows easy display of current values of Employee object's name and salary instance variables. 
	• Involves the printEmp method		
	• Expected outcome: Prints specific name and salary of the Employee object.
```java
public void printEmp() { 
System.out.println("name : " + name ); // Accesses the 'name' instance variable System.out.println("salary :" + salary); // Accesses the 'salary' instance variable }
```

5. **Create the Actual `employee` object in main**
	• Creates an actual Employee object in the main method. 
	• Employee empOne is created with a name variable set to "Ransika" and a salary variable defaulting to 0.0.
	 • The constructor sets empOne.name to "Ransika".
```java
public static void main(String args[]) { 
Employee empOne = new Employee("Ransika");
empOne.setSalary(1000); // Sets the value for the Salary
// Creates a new Employee object named 'empOne' // The constructor sets empOne.name to "Ransika" // ... rest of main }
```

![[J2 - Java Variables 2025-06-11 12.16.51.excalidraw]]

—
- Class / Static Variables
	• Class variables, or static variables, are declared outside of methods, constructors, or blocks.  
	• Each class has one copy of each class variable.  
	• Used rarely except as constants, which are public/private, final, and static.  
	• Stored in static memory, created when the program starts and destroyed when it stops.  
	• Visibility is similar to instance variables, but most are public.  
	• Default values are the same as instance variables, with default values for numbers, Booleans, and object references.  
	• Accessible by calling the class name ClassName.VariableName.  
	• When declared as public static final, variable names are in upper case.

```java
import java.io.*; public class Employee { // salary variable is a private static variable 
private static double salary; 
// DEPARTMENT is a constant 
public static final String DEPARTMENT = "Development "; public static void main(String args[]) { salary = 1000; System.out.println(DEPARTMENT + "average salary:" + salary); } }
```

---

## Java Data Types
- [[#Unicode System|Unicode System]]
(Primitive = Basic/fundamental)
Primitive data types are defined by the language and named by a keyword:
- **Byte:**
	- Minimum Value: -128 - Maximum Value: 128 (Inclusive)
	`byte a = 100; byte b = -50`
	- Default value is 0
	- FOUR times smaller than an integer
		- Beneficial for Saving Memory
- **Short:**
	- Provides a range of values from. {-32,768 to 32,767} (inclusive)
	- Default value is 0
	- Beneficial for Saving Memory
	`short s = 10000; short r = -20000;`
- **Int:**
	• 32-bit signed two's complement integer. 
	• Allows wide range of values from -2,147,483,648 (-231) to 2,147,483,647 (inclusive) (231 -1). 
	• Default value for int variable is 0.
- **long:**
	• 64-bit signed two's complement integer. 
	• Can represent vast range from -9,223,372,036,854,775,808 (-263) to 9,223,372,036,854,775,807 (inclusive) (263 -1). 
	• Used for wider range than int. 
	•Default value is 0L.
- **Float:**
	• Single-precision 32-bit IEEE 754 floating-point representation. 
	• Ideal for large arrays of floating-point numbers. 
	• Default value: 0.0f. 
	• Not suitable for precise values due to rounding errors.
**Double Data Type Overview** 
	• Double-precision 64-bit IEEE 754 floating-point representation. 
	• Default for decimal values. 
	• Not suitable for precise values like currency. 
	• Default value is 0.0d.
**Boolean Data Type Overview**  
	• Represents single bit of information.  
	• Can hold true or false values.  
	• Used for simple flags tracking true/false conditions.  
	• Default value is false.
**Char Data Type Overview** 
	• Single 16-bit Unicode character. 
	• Represents diverse languages and symbols.
	 • Ranges from '\u0000' to '\uffff'. 
	 • Primarily used for character storage.

*Delcaring and Initializing a variable*:
```java
int myAge; // Declaring
myAge = 30; // Initializing

// OR
double price = 19.99;
boolean isValud = true;
char initial = 'j';
```

*Type Casting/ Changing (Manual/ Automatic)*
1. **Widening Conversion (Auto)**: Basically you initialize the variable of your choice with its initial data type, such as `int`, then create a new variable and assign the first to it (`long`) and so on.
```cpp
int smallNum = 10;
long bigNum = smallNum;
double decimalNum = smallNum;
```
2. **Narrowing Conversion (Manual)**:  Requires the user to instruct java to convert a larger type to a smaller type. This is done by placing the target DT in parenthesis before the value. `(dataType)value`. Can lead to loss of information
```java
double largeDecimal = 99.99;
int wholeNumber = (int) largeDecimal; // Manual (narrowing) conversion. 'wholeNumber' will be 99.
                                    // The decimal part .99 is lost.

int bigInteger = 200;
byte smallByte = (byte) bigInteger; // Manual (narrowing) conversion.
                                  // 200 is outside byte's range (-128 to 127), so 'smallByte' will be -56
                                  // (this is called overflow/underflow, and it's a reason for caution with casting).
```

---
### Unicode System
Allows for developers to work with applications using diverse languages and scripts.
1. **ASCII** → United States Unicode
2. **ISO 8859-1** → Western European Language
3. **KOI-8** → Russian
4. **GB1830 & BIG-5** → Chinese

(Not Going In depth (Unnecesary))










---
## Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on::
```cardlink
url: https://www.tutorialspoint.com/java/java_variable_types.htm
title: "Java Variable Types"
description: "Java Variable Types - Discover the different types of variables in Java, including primitive and reference types, with examples and best practices."
host: www.tutorialspoint.com
favicon: https://www.tutorialspoint.com/images/favicon.ico
image: https://www.tutorialspoint.com/images/tp_logo_436.png
```

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see:: [[J1 - Java Basics]]

**Terms**
<!-- Links to definition pages. -->
- [[D2 - Terms & Definitions]]

---
**Template Help**
<!-- Links to external help pages on GitHub. -->
- [Basic Template Structure](https://github.com/groepl/Obsidian-Templates#basic-template-structure)
- [How to Use Links](https://github.com/groepl/Obsidian-Templates#how-to-use-links)
- [How to Use Tags](https://github.com/groepl/Obsidian-Templates#how-to-use-tags)
- [How to Search Notes](https://github.com/groepl/Obsidian-Templates#how-to-search-notes)
- [Plugins Needed](https://github.com/groepl/Obsidian-Templates#obsidian-plugins-needed)
- [Find Latest Updates](https://github.com/groepl/Obsidian-Templates)

// Entr Command
```sh
while true; do javac -d bin src/*.java && java -cp bin ShelterApp; sleep 2; done
```
