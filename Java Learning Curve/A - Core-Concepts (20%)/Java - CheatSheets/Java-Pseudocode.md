---
created: 2025-06-29T01:18
updated: 2025-06-29T16:37
---
# Java Pseudocode Cheatsheet

## Table of Contents
1. [Basic Structure](#basic-structure)
2. [Variable Declarations](#variable-declarations)
3. [Control Structures](#control-structures)
4. [Methods/Functions](#methodsfunctions)
5. [Object-Oriented Constructs](#object-oriented-constructs)
6. [Data Structures](#data-structures)
7. [Exception Handling](#exception-handling)
8. [Documentation Rules](#documentation-rules)
9. [Best Practices](#best-practices)

---

## Basic Structure

### Program Structure
```
PROGRAM ProgramName
    IMPORT required libraries
    
    DECLARE global variables
    
    MAIN METHOD
        // Main logic here
    END MAIN
    
    // Additional methods
END PROGRAM
```

### Class Structure
```
CLASS ClassName EXTENDS ParentClass IMPLEMENTS Interface
    // Class-level variables
    PRIVATE fieldType fieldName
    PUBLIC fieldType fieldName
    
    // Constructor
    CONSTRUCTOR ClassName(parameters)
        // Initialization logic
    END CONSTRUCTOR
    
    // Methods
    PUBLIC returnType methodName(parameters)
        // Method logic
    END METHOD
END CLASS
```

---

## Variable Declarations

### Basic Declarations
```
DECLARE dataType variableName
DECLARE dataType variableName = initialValue

// Examples:
DECLARE int count = 0
DECLARE String name = "John"
DECLARE boolean isValid = false
DECLARE double[] prices = new array of size 10
```

### Constants
```
DECLARE CONSTANT dataType CONSTANT_NAME = value

// Example:
DECLARE CONSTANT int MAX_SIZE = 100
```

---

## Control Structures

### Conditional Statements

#### If-Else
```
IF condition THEN
    // statements
ELSE IF condition THEN
    // statements
ELSE
    // statements
END IF
```

#### Switch
```
SWITCH variable
    CASE value1:
        // statements
        BREAK
    CASE value2:
        // statements
        BREAK
    DEFAULT:
        // statements
        BREAK
END SWITCH
```

### Loops

#### For Loop
```
FOR initialization; condition; increment DO
    // loop body
END FOR

// Enhanced for loop
FOR EACH element IN collection DO
    // process element
END FOR
```

#### While Loop
```
WHILE condition DO
    // loop body
END WHILE
```

#### Do-While Loop
```
DO
    // loop body
WHILE condition
```

---

## Methods/Functions

### Method Declaration
```
ACCESS_MODIFIER STATIC returnType methodName(parameterType parameterName, ...)
    DECLARE local variables
    
    // Method logic
    
    RETURN value (if not void)
END METHOD
```

### Method Examples
```
PUBLIC int calculateSum(int a, int b)
    DECLARE int result = a + b
    RETURN result
END METHOD

PRIVATE void displayMessage(String message)
    PRINT message
END METHOD

PUBLIC STATIC void main(String[] args)
    // Program entry point
END METHOD
```

---

## Object-Oriented Constructs

### Class Definition
```
PUBLIC CLASS Student
    // Fields
    PRIVATE String name
    PRIVATE int age
    PRIVATE double gpa
    
    // Constructor
    PUBLIC CONSTRUCTOR Student(String name, int age, double gpa)
        SET this.name = name
        SET this.age = age
        SET this.gpa = gpa
    END CONSTRUCTOR
    
    // Getter methods
    PUBLIC String getName()
        RETURN name
    END METHOD
    
    // Setter methods
    PUBLIC void setName(String name)
        SET this.name = name
    END METHOD
    
    // Other methods
    PUBLIC void displayInfo()
        PRINT "Name: " + name
        PRINT "Age: " + age
        PRINT "GPA: " + gpa
    END METHOD
END CLASS
```

### Inheritance
```
PUBLIC CLASS GraduateStudent EXTENDS Student
    PRIVATE String thesisTitle
    
    PUBLIC CONSTRUCTOR GraduateStudent(String name, int age, double gpa, String thesis)
        CALL SUPER(name, age, gpa)
        SET this.thesisTitle = thesis
    END CONSTRUCTOR
    
    PUBLIC void displayThesis()
        PRINT "Thesis: " + thesisTitle
    END METHOD
END CLASS
```

---

## Data Structures

### Arrays
```
// Declaration and initialization
DECLARE dataType[] arrayName = new array of size n
DECLARE dataType[] arrayName = {value1, value2, value3}

// Access and modification
SET arrayName[index] = value
DECLARE element = arrayName[index]

// Iteration
FOR i = 0 TO arrayName.length - 1 DO
    PROCESS arrayName[i]
END FOR
```

### Collections

#### ArrayList
```
DECLARE ArrayList<dataType> listName = new ArrayList<>()

// Operations
CALL listName.add(element)
CALL listName.remove(index)
DECLARE element = listName.get(index)
DECLARE size = listName.size()

FOR EACH element IN listName DO
    PROCESS element
END FOR
```

#### HashMap
```
DECLARE HashMap<KeyType, ValueType> mapName = new HashMap<>()

// Operations
CALL mapName.put(key, value)
DECLARE value = mapName.get(key)
DECLARE exists = mapName.containsKey(key)

FOR EACH key IN mapName.keySet() DO
    DECLARE value = mapName.get(key)
    PROCESS key and value
END FOR
```

---

## Exception Handling

### Try-Catch-Finally
```
TRY
    // Risky code that might throw exception
CATCH ExceptionType1 e
    // Handle specific exception
CATCH ExceptionType2 e
    // Handle another specific exception
CATCH Exception e
    // Handle general exception
FINALLY
    // Cleanup code (always executes)
END TRY
```

### Throwing Exceptions
```
PUBLIC void methodName() THROWS ExceptionType
    IF error_condition THEN
        THROW new ExceptionType("Error message")
    END IF
END METHOD
```

---

## Documentation Rules

### Method Documentation Template
```
/**
 * PURPOSE: Brief description of what the method does
 * PRECONDITIONS: What must be true before calling this method
 * POSTCONDITIONS: What will be true after the method executes
 * PARAMETERS:
 *   - parameterName: description of parameter
 * RETURNS: description of return value
 * THROWS: exceptions that might be thrown
 */
PUBLIC returnType methodName(parameters)
    // Method implementation
END METHOD
```

### Class Documentation Template
```
/**
 * CLASS: ClassName
 * PURPOSE: Brief description of the class's responsibility
 * INVARIANTS: Properties that must always be true for objects of this class
 * AUTHOR: Your name
 * DATE: Creation date
 */
PUBLIC CLASS ClassName
    // Class implementation
END CLASS
```

### Algorithm Documentation
```
/**
 * ALGORITHM: Algorithm name (e.g., Binary Search)
 * INPUT: Description of input parameters
 * OUTPUT: Description of output/return value
 * TIME COMPLEXITY: O(notation)
 * SPACE COMPLEXITY: O(notation)
 * STEPS:
 *   1. Step description
 *   2. Step description
 *   3. Step description
 */
```

---

## Best Practices

### 1. Structure Rules
- Use consistent indentation (2 or 4 spaces)
- Align related elements vertically
- Group related operations together
- Separate logical sections with blank lines

### 2. Naming Conventions
```
// Variables and methods: camelCase
DECLARE int studentCount
PUBLIC void calculateGrade()

// Constants: UPPER_SNAKE_CASE
DECLARE CONSTANT int MAX_STUDENTS = 30

// Classes: PascalCase
CLASS StudentManager
```

### 3. Comment Guidelines
```
// Single-line comments for brief explanations
/* Multi-line comments for detailed explanations */

// Good commenting examples:
DECLARE int count = 0  // Track number of valid entries

// Calculate average score across all students
FOR EACH student IN studentList DO
    SET totalScore = totalScore + student.getScore()
END FOR
DECLARE double average = totalScore / studentList.size()
```

### 4. Modular Design Principles

#### Function Decomposition
```
// Break complex operations into smaller functions
PUBLIC void processStudentData()
    CALL readStudentFile()
    CALL validateStudentData()
    CALL calculateStatistics()
    CALL generateReport()
END METHOD
```

#### Single Responsibility
```
// Each method should have one clear purpose
PUBLIC double calculateAverage(double[] scores)
    // Only calculates average, nothing else
END METHOD

PUBLIC void displayResults(double average)
    // Only displays results, nothing else
END METHOD
```

### 5. Adaptability Patterns

#### Configuration Parameters
```
// Use constants for easy modification
DECLARE CONSTANT int DEFAULT_CAPACITY = 10
DECLARE CONSTANT String DEFAULT_FORMAT = "yyyy-MM-dd"
```

#### Generic Templates
```
// Design for reusability
PUBLIC CLASS DataProcessor<T>
    PUBLIC void process(List<T> data)
        // Generic processing logic
    END METHOD
END CLASS
```

### 6. Error Handling Standards
```
// Always validate input
PUBLIC void processAge(int age)
    IF age < 0 OR age > 150 THEN
        THROW new IllegalArgumentException("Invalid age: " + age)
    END IF
    // Process valid age
END METHOD

// Provide meaningful error messages
CATCH FileNotFoundException e
    PRINT "Error: Could not find file: " + filename
    PRINT "Please check the file path and try again"
END CATCH
```

---

## Quick Reference Template

### Complete Method Template
```
/**
 * PURPOSE: [What this method does]
 * PRECONDITIONS: [What must be true before calling]
 * POSTCONDITIONS: [What will be true after execution]
 * PARAMETERS: [Parameter descriptions]
 * RETURNS: [Return value description]
 * THROWS: [Possible exceptions]
 */
PUBLIC returnType methodName(parameterType parameterName)
    // Input validation
    IF invalid_input THEN
        THROW appropriate_exception
    END IF
    
    // Declare local variables
    DECLARE variables_needed
    
    // Main algorithm logic
    // Step 1: [Description]
    // Step 2: [Description]
    // Step 3: [Description]
    
    // Return result (if applicable)
    RETURN result
END METHOD
```

This cheatsheet provides a solid foundation for writing clear, well-documented pseudocode that translates effectively to Java implementation.
