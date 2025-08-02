# Java Exception Hierarchy
![[J11 - Exception Handling 2025-08-02 06.52.59.excalidraw]]
**Throwable Class** - Root class of the hierarchy. 

---
1. *Errors:* Represents irrecoverable conditions in (JVM) running out of memory, memory leaks, stack overflow errors, library compatibility, infinite recursion, etc.
2. *Exceptions*: Can be caught and handled by the program.
	1. When an exception occur, an object is created (Exception Object)
	2. Contains information such as (Name & Description) of the exception and state of the program when it occured.
3. *Exception Types*: `RuntimeException` & `IOExcption`
	1. `RuntimeException` - Happens due to a programming error (Unchecked Exceptions)
		1. Not checked during compile or run time
		2. Improper use of an API (`IllegalArgumentException`), Null pointer access (`NullPointerExcepiton`) _variable Init or Declaration_, Out of bounds array access (`ArrayIndexOutOfBoundsException`)_Used In existing Elements_, Dividing a Number by 0 (`Arithmetic Exception`)
		3. **Analogy**: 'If a runtime exception happened, its your fault'
	2. `IOException` - Checked Exception. 
		1. Checked by the compiler. Programmer is prompted to handle exceptions.
		2. Trying to open a file that does not exist (`FileNotFoundException`), Trying to read past the end of the file.
---
# Files Related to this Content
1. [[J11.1 - Java Exceptions]]
2. [[J11.2 - Java Annotation Types]]
3. [[J11.3 - Java Logging]]



> [!NOTE] 💡Tip 
> Look further into Assertions if they interest you. Personally, I do not use them as often as I would like. I prefer logging and Try blocks. However it is good to learn a way to test for bugs before they happen.


