---
Title: D2 - Terms & Definitions
Topic: Java Learning Curve
tags:
  - programming/java
  - theme/reference
  - type/term
created: 2025-06-06T14:20
updated: 2025-06-06T14:25
---

- **lock of Code**: Pronounced: `blok uv kohd`. A group of programming statements enclosed within curly braces `{}`.
- **Bytecode**: Pronounced: `byt-kohd`. A special low-level code that Java programs are converted into when compiled. This code can then be run on any device with a Java Virtual Machine.
- **CamelCase**: Pronounced: `kam-uhl-keys`. A naming convention where the first letter of the first word is lowercase, and the first letter of each subsequent word is uppercase (e.g., `myVariableName`).
- **Class**: Pronounced: `klahs`. In Java, a blueprint or template for creating objects. It defines the characteristics and behaviors that objects of that class will have.
- **Compile**: Pronounced: `kuhm-pyl`. The process of translating source code (what you write) into machine-readable code (**bytecode** in Java).
- **Compilation Error**: Pronounced: `kom-pi-ley-shun er-or`. An error detected by the compiler during the compilation process, preventing the program from being converted into **bytecode**.
- **Console**: Pronounced: `kon-sohl`. The text-based interface (like Command Prompt or Terminal) where you run programs and see their text output.
- **Data Type (`dataType`)**: Pronounced: `dah-tuh typ`. Specifies the kind of data a variable can hold (e.g., `int` for whole numbers, `String` for text, `boolean` for true/false).
- **Declare**: Pronounced: `dih-klair`. To tell the computer that you want to create a variable and specify its name and **data type**.
- **Initialize**: Pronounced: `ih-nish-uh-lyz`. To give a variable its first value.
    
- **Java Development Kit (JDK)**: Pronounced: `jah-vuh dih-vel-uhp-muhnt kit`. A software package that provides all the tools needed to write, compile, and run Java programs.
- **Java Virtual Machine (JVM)**: Pronounced: `jah-vuh vur-choo-uhl muh-sheen`. A virtual computer that runs Java **bytecode**. It allows Java programs to run on different operating systems without modification.
- **Local Variable**: Pronounced: `loh-kuhl vair-ee-uh-bul`. A variable that is declared inside a **method** or a **block of code** and is only accessible within that specific method or block.
- **Main Method**: Pronounced: `meyn meth-uhd`. The special method `public static void main(String[] args)` where a Java application begins its execution.
- **Method**: Pronounced: `meth-uhd`. A collection of statements that are grouped together to perform an operation.
    
- **Parameter**: Pronounced: `puh-ram-ih-ter`. A variable defined in the declaration of a method, used to receive values (arguments) when the method is called.
- **Program**: Pronounced: `proh-gram`. A set of instructions that a computer can follow to perform a task.
- **Scope**: Pronounced: `skohp`. The region of a program where a variable is accessible. For **local variables**, it's limited to the **block of code** where they are declared.
    
- **Variable**: Pronounced: `vair-ee-uh-bul`. A named storage location in a computer's memory that can hold a value, which can change during program execution.

**Related To**: [[D2 - Terms & Definitions]]

---
`set` method: A method used to set or change the value of an instance variable
```java
public void setSalary(double empSal) { // This is a setter method
   salary = empSal; // Assigns the passed value to the instance variable 'salary'
}
```
- Allows you to update instance method
`print` method: Used to display the values of an instance method
```java
public void printEmp() { // This method prints instance variable values
   System.out.println("name  : " + name );
   System.out.println("salary :" + salary);
}
```
- Accesses the Name and Salary Instance methods of the Specific Employee Class object and prints their values.

---
## Variable Keywords
**Refer To:** [[J2 - Java Variables]]
- **Access Modifier**: Pronounced: `ak-ses mod-uh-fahy-er`. Keywords (`public`, `private`, etc.) that control where classes, methods, or variables can be used. (Not directly covered in this topic but relevant to `public` in the example).
- **Bit**: Pronounced: `bit`. The smallest unit of digital information, representing either `0` or `1`.
- **Boolean (`boolean`)**: Pronounced: `boo-lee-uhn`. A **primitive data type** that can only store `true` or `false` values.
- **Byte (`byte`)**: Pronounced: `byt`. A **primitive data type** that stores whole numbers from -128 to 127. It uses 1 byte of memory (8 bits).
- **Casting**: Pronounced: `kas-ting`. The explicit process of converting a value from one data type to another. It's often required when converting from a larger data type to a smaller one (narrowing conversion).
- **`char`**: Pronounced: `kar` or `char`. A **primitive data type** that stores a single Unicode character, enclosed in single quotes (e.g., `'A'`, `'5'`, `'$'`). It uses 2 bytes of memory.
- **Class**: Pronounced: `klahs`. In Java, a blueprint or template for creating objects.
- **Compilation Error**: Pronounced: `kom-pi-ley-shun er-or`. An error detected by the Java compiler that prevents your code from being converted into executable form.
- **Console**: Pronounced: `kon-sohl`. The text-based interface (like Command Prompt or Terminal) where you run programs and see their text output.
- **Data Type (`dataType`)**: Pronounced: `dah-tuh typ`. A classification that specifies which type of value a variable can hold (e.g., number, text, true/false) and the operations that can be performed on it.
- **Declare**: Pronounced: `dih-klair`. To tell the computer that you want to create a variable and specify its name and **data type**.
- **`double`**: Pronounced: `duh-bul`. A **primitive data type** for storing numbers with decimal points (floating-point numbers) with high precision (about 15 decimal places). It uses 8 bytes of memory. This is the default decimal type in Java.
- **`float`**: Pronounced: `floht`. A **primitive data type** for storing numbers with decimal points (floating-point numbers) with less precision (about 6-7 decimal places) than `double`. It uses 4 bytes of memory and requires an `f` or `F` suffix for literals.
- **Initialize**: Pronounced: `ih-nish-uh-lyz`. To give a variable its first value.
- **`int`**: Pronounced: `int`. A **primitive data type** for storing whole numbers. It is the most commonly used integer type and uses 4 bytes of memory.
- **Java Development Kit (JDK)**: Pronounced: `jah-vuh dih-vel-uhp-muhnt kit`. A software package that provides all the tools needed to write, compile, and run Java programs.
- **Literal**: Pronounced: `lit-uh-ruhl`. A fixed value that directly appears in your code (e.g., `5`, `3.14`, `true`, `'A'`, `"Hello"`).
- **`long`**: Pronounced: `long`. A **primitive data type** for storing very large whole numbers. It uses 8 bytes of memory and typically uses an `L` or `l` suffix for literals.
- **Main Method**: Pronounced: `meyn meth-uhd`. The special method `public static void main(String[] args)` where a Java application begins its execution.
- **Overflow**: Pronounced: `oh-ver-floh`. Occurs when a number becomes too large to be stored in its assigned data type, causing it to wrap around to the minimum value.
- **Primitive Data Types**: Pronounced: `prim-uh-tiv dah-tuh typs`. The 8 fundamental, built-in data types in Java that store simple, single values (e.g., `int`, `double`, `boolean`, `char`).
- **Program**: Pronounced: `proh-gram`. A set of instructions that a computer can follow to perform a task.
- **`short`**: Pronounced: `short`. A **primitive data type** for storing whole numbers. It uses 2 bytes of memory.
- **Underflow**: Pronounced: `uhn-der-floh`. Occurs when a number becomes too small (negative) to be stored in its assigned data type, causing it to wrap around to the maximum value.
- **Unicode**: Pronounced: `yoo-ni-kohd`. An international standard for representing characters from various languages and scripts. Java's `char` type uses Unicode.
- **Variable**: Pronounced: `vair-ee-uh-bul`. A named storage location in a computer's memory that can hold a value, which can change during program execution.

---
## If - Else Statements
1. **Statement**: (STAYT-ment) A single instruction in a program that tells the computer to perform an action. Ends with a semicolon `;`.
2. **Keyword**: (KEY-werd) A word that has a special meaning in a programming language and cannot be used for other purposes (like variable names). Examples: `if`, `else`, `public`, `class`.
3. - **Condition**: (kun-DISH-un) A statement or expression that can be evaluated as either true or false.
	- **`else` Statement**: (els STAYT-ment) A keyword used with an `if` statement to define a block of code that runs when the `if` condition is false.
	- **`if` Statement**: (if STAYT-ment) A keyword used to define a block of code that runs only if a specified condition is true.
4. **Code Block**: (koad blok) A group of programming statements, usually enclosed in curly braces `{}`. These statements are treated as a single unit.
5. **Comparison Operator**: (kum-PAIR-ih-sun OP-er-ay-tor) A symbol that compares two values and tells you if the comparison is true or false. Examples: (=-=), `>`, `<`.
6. **Compile**: (kum-PILE) To translate human-readable source code (like your `.java` file) into machine-readable code (like a `.class` file) that a computer can run.

---
## Java Object Oriented
Source:: [[J6 - Object Oriented Programming]]
1. **Class**: A blueprint from which individual objects are created.
2. **Object**: An entity that has two characteristics (states & Behaviors). An object is a variable of the type class, it is a basic component of an OOP system.
3. **Inheritance**: Process by which we a developer can reuse the functionalities of the existing classes to new classes. 
	1. (Parent) class 
	2. (Child) class.
4. **Polymorphism (Many Forms)**: Useful when a developer wants to create multiple forms with the same name of a single entity.
	1. **Method Overloading:** Performed in the same class where Java have multiple methods with the same name but different parameters, whereas
	2. **Method Overriding**: Performed by using the inheritance where multiple developers have multiple methods with the same name in parent and child classes.
5. **Abstraction:** Technique of hiding internal details and showing functionalities. 
6. **Encapsulation**: Process of binding the data members (Attributes) and methods toghether.
	1. (public) - Global Access
	2. (private) - Class Internal Access



---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on::[[Java Index]]

---
**Tasks**
<!-- What remains to be done with this note? --> 
-Use this as your own template. Feel free to fill it up with more terms as you go. I will improve this. 

---
**Template Help**
<!-- Links to external help pages on GitHub. -->
- [Basic Template Structure](https://github.com/groepl/Obsidian-Templates#basic-template-structure)
- [How to Use Links](https://github.com/groepl/Obsidian-Templates#how-to-use-links)
- [How to Use Tags](https://github.com/groepl/Obsidian-Templates#how-to-use-tags)
- [How to Search Notes](https://github.com/groepl/Obsidian-Templates#how-to-search-notes)
- [Plugins Needed](https://github.com/groepl/Obsidian-Templates#obsidian-plugins-needed)
- [Find Latest Updates](https://github.com/groepl/Obsidian-Templates)