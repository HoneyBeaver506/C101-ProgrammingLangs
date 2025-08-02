---
Title: C++ Pointers & Reference
Topic: C++ Learning Curve
aliases:
  - Pointers & Reference
tags:
  - programming/cpp
  - theme/concept
  - type/note
  - type/sketchnote
created: 2025-06-06T23:40
updated: 2025-06-29T16:24
template_type: Frontmatter
template_version: "1.12"
---
# C++ Pointers and Reference
*Table of Contents:*


---

## 🎯 What & Why
**Purpose**:
- **Pointers:** A pointer is a variable that stores the memory address of another variable. They are a powerful feature that allows for direct memory manipulation, dynamic memory allocation, and passing large data structures to functions efficiently. Pointers are a fundamental concept in C and C++, but their flexibility can lead to errors like null dereferences and dangling pointers if not managed carefully.
- **References:** A reference is an alias, or another name, for an already existing variable. Once a reference is initialized, it acts as the original variable itself. Any operation performed on the reference directly affects the original variable. References provide a cleaner and safer way to work with indirection compared to pointers, especially for function parameters.

**Use When:** 

**Analogy:**
- A **pointer** is like a piece of paper with the house's street address written on it. You can change the address on the paper to point to a different house, or you can have no address on the paper at all (a null pointer). To go inside the house, you have to use the address on the paper.
- A **reference** is like a nickname for the house. Once you give the house a nickname, you can't use that nickname for another house. Using the nickname is the same as using the original name—you are always referring to the same house.

---

## ⚡ Core Syntax
```C++
#include <iostream>

int main() {
    int x = 10;
    
    // --- Pointers ---
    // Declaration and initialization
    int* p = &x; // 'p' stores the address of 'x'
    
    std::cout << "Value of x: " << x << std::endl;      // Output: 10
    std::cout << "Address of x: " << &x << std::endl;   // Output: (e.g., 0x7ffc34c)
    std::cout << "Value of p (address): " << p << std::endl; // Output: (e.g., 0x7ffc34c)
    std::cout << "Value at address pointed to by p: " << *p << std::endl; // Output: 10
    
    // Changing value via pointer
    *p = 20;
    std::cout << "New value of x: " << x << std::endl; // Output: 20
    
    // --- References ---
    // Declaration and initialization
    int& r = x; // 'r' is an alias for 'x'
    
    std::cout << "Value of x: " << x << std::endl;      // Output: 20
    std::cout << "Value of r: " << r << std::endl;      // Output: 20
    std::cout << "Address of x: " << &x << std::endl;   // Output: (e.g., 0x7ffc34c)
    std::cout << "Address of r: " << &r << std::endl;   // Output: (e.g., 0x7ffc34c)
    
    // Changing value via reference
    r = 30;
    std::cout << "New value of x: " << x << std::endl; // Output: 30

    // Pointers can be reassigned, references cannot
    int y = 50;
    p = &y; // p now points to y
    // r = y; // This would assign the value of y to x, not rebind r to y
    std::cout << "Value at address pointed to by p (now y): " << *p << std::endl; // Output: 50
    
    return 0;
}
```

---
## 🔧 Essential Methods
A common use case for both pointers and references is to pass arguments to functions by "reference" (in a general sense) to avoid copying large objects and to allow the function to modify the original variable.

**Call by Pointer:** This method uses pointers as function parameters. The function receives the memory address of the original variable. To access or modify the value, you must dereference the pointer using the `*` operator. This approach requires a null check to avoid a segmentation fault.
```c++
#include <iostream>

void incrementWithPointer(int* ptr) {
    // It's a good practice to check for nullptr before dereferencing
    if (ptr != nullptr) {
        (*ptr)++;
    }
}

int main() {
    int value = 5;
    std::cout << "Before: " << value << std::endl; // Output: 5
    
    incrementWithPointer(&value); // Pass the address of 'value'
    
    std::cout << "After: " << value << std::endl;  // Output: 6
    return 0;
}
```

**Call by Reference:** This method uses references as function parameters. The function receives an alias for the original variable. The syntax inside the function is cleaner and identical to working with the variable directly. References are safer because they cannot be null.
```c++
#include <iostream>

void incrementWithReference(int& ref) {
    ref++; // No dereferencing needed
}

int main() {
    int value = 5;
    std::cout << "Before: " << value << std::endl; // Output: 5
    
    incrementWithReference(value); // Pass the variable directly
    
    std::cout << "After: " << value << std::endl;  // Output: 6
    return 0;
}
```

---
## ⚖️ Quick Pros/Cons
*Advantages:*
(Pointer)
- **Flexibility:** Pointers can be reassigned to point to different variables, making them ideal for dynamic data structures like linked lists and trees.
- **Nullable:** A pointer can be assigned the value `nullptr`, which explicitly represents "no object" or "no address". This is useful for optional parameters or to check if a pointer is valid before use.
- **Arithmetic:** Pointers support arithmetic operations, which is crucial for iterating through arrays and managing contiguous blocks of memory.
- **Dynamic Memory:** Pointers are essential for dynamic memory allocation on the heap using the `new` and `delete` operators.

(Reference)
- **Safer by Design:** A reference must be initialized when declared and cannot be `nullptr`. This eliminates the risk of null pointer dereference errors.
- **Simpler Syntax:** References do not require explicit dereferencing with the `*` operator; they are used exactly like the variable they refer to, making the code cleaner and easier to read.
- **Unchangeable:** A reference cannot be reassigned to alias a different variable after its initial declaration. This guarantees that it always refers to the same object.
- **Efficient Passing:** References are the preferred method for passing large objects to functions without the performance cost of copying, while still allowing the function to modify the original object.

*Disadvantages:*

(Pointer)
- **Safety Risks:** Pointers are prone to errors such as null pointer dereferences, dangling pointers (pointing to deallocated memory), and memory leaks if not managed correctly.
- **Complex Syntax:** The use of `*` for both declaration and dereferencing, and `&` for the address-of operator, can be confusing and lead to syntax errors for beginners.
- **Manual Management:** Raw pointers require the programmer to manually manage memory with `new` and `delete`, which can be a source of bugs.

(Reference)
- **Cannot Be Uninitialized:** References must always be bound to a valid object at the time of declaration, making them unsuitable for scenarios where a variable might not yet exist or be optional.
- **Lack of Flexibility:** Because a reference cannot be reassigned, they are not suitable for algorithms or data structures that require changing what an alias refers to, such as iterating through a list.
- **No Arithmetic:** Reference arithmetic is not possible, as a reference is not a memory address that can be manipulated.

---

## 🐛 Common Issues
1. **Dangling Pointers:** A pointer that points to a memory location that has been deallocated or has gone out of scope. Dereferencing a dangling pointer leads to undefined behavior.
    - **Solution:** Set the pointer to `nullptr` immediately after deallocating the memory with `delete`.
    ```c++
    int* ptr = new int(10);
    delete ptr;
    ptr = nullptr; // Prevents the pointer from being a dangling pointer
    ```
    
2. **Null Pointer Dereference:** Accessing the value of a pointer that has a `nullptr` value. This is a common cause of segmentation faults.
    - **Solution:** Always check if a pointer is not `nullptr` before dereferencing it.
    ```c++
    int* ptr = nullptr;
    // ... later in the code
    if (ptr != nullptr) {
        *ptr = 20; // This is now safe
    }
    ```
    
3. **Invalid References:** While a reference cannot be null, you can create a "dangling reference" by returning a reference to a local variable that is destroyed when the function exits.
    - **Solution:** Never return a reference to a local variable.
    ```c++
    int& createDanglingReference() {
        int x = 10;
        return x; // BAD: x is destroyed here, the reference is now dangling
    }
    ```

---

## 💡 Key Tips
- **Use References When You Can, Pointers When You Have To:** This is a common C++ idiom. Prefer references for function parameters to avoid copies and for cleaner syntax. Use pointers when you need to represent "no object" (`nullptr`), for dynamic memory allocation, or when you need to reassign the address.
- **Use `nullptr` for Pointers:** Always initialize pointers to `nullptr` if they are not immediately assigned a valid address. This makes it explicit that the pointer doesn't point to a valid object.
- **Use Smart Pointers in Modern C++:** For dynamic memory management, modern C++ (C++11 and later) provides smart pointers like `std::unique_ptr` and `std::shared_ptr`. They automatically manage memory deallocation, making code safer and preventing memory leaks.
- **`const` Pointers and References:**
    - **`const int* p;`**: Pointer to a constant integer. You cannot change the value at the address `p` points to.
    - **`int* const p;`**: Constant pointer to an integer. You cannot change the address `p` holds, but you can change the value at that address.
    - **`const int& r;`**: Constant reference. You cannot change the value of the aliased variable through this reference.
---

# Diagram 
1. **Pointer to Memory**
![[C++ Pointers & Reference 2025-08-02 09.10.18.excalidraw]]
**Explanation:** The variable `x` is on the stack. The pointer `p` is also on the stack, but its value is a memory address, `0x5000`. This address points to a dynamically allocated integer on the heap. The arrow from `p` to the heap shows the pointer "pointing" to the memory. The diagram also shows that `p` has its own address (`0x1004`), distinct from the variable it points to.

2. **Reference in Memory**

![[C++ Pointers & Reference 2025-08-02 09.14.46.excalidraw]]
The variable `x` is on the stack. The reference `r` is an alias for `x` and shares the same memory address. The diagram shows this by having the `r` and `x` variables linked to the same memory location, illustrating that `r` is just another name for `x` and doesn't have its own distinct memory address in the same way a pointer does.





> [!NOTE] ☁️ Programmer Thoughts
> I had quite the hard time understanding pointers. So I recapped and only focused on the core concepts. Pointers are not difficult once you learn how to use them correctly. I personally found out that using diagrams is a great way to learn pointers.




---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on:: Programmiz - Pointer and Reference

```cardlink
url: https://www.programiz.com/cpp-programming/pointers
title: "C++ Pointers (With Examples)"
description: "Pointers are variables that store the memory addresses of other variables. In this tutorial, we will learn about pointers in C++ with the help of examples."
host: www.programiz.com
```

- based_on:: Tutorialsploit - Pointers & Reference

```cardlink
url: https://www.tutorialspoint.com/cplusplus/cpp_pointers.htm
title: "C++ Pointers"
description: "Learn about C++ pointers, their types, syntax, and how to effectively use them in your programming. Explore practical examples and enhance your C++ skills."
host: www.tutorialspoint.com
favicon: https://www.tutorialspoint.com/images/favicon.ico
image: https://www.tutorialspoint.com/images/tp_logo_436.png
```


**Terms**
<!-- Links to definition pages. -->
-  [[D1 - Terms & Definitions]]


---
**Tasks**
<!-- What remains to be done with this note? --> 
- Pointers can be dangerous if not used correctly. Read through the concept until you understand how it works.
- You can use the following link to test and use pointer without the risk: [Compiler Explorer](https://godbolt.org/)


---
**Template Help**
<!-- Links to external help pages on GitHub. -->
- [Basic Template Structure](https://github.com/groepl/Obsidian-Templates#basic-template-structure)
- [How to Use Links](https://github.com/groepl/Obsidian-Templates#how-to-use-links)
- [How to Use Tags](https://github.com/groepl/Obsidian-Templates#how-to-use-tags)
- [How to Search Notes](https://github.com/groepl/Obsidian-Templates#how-to-search-notes)
- [Plugins Needed](https://github.com/groepl/Obsidian-Templates#obsidian-plugins-needed)
- [Find Latest Updates](https://github.com/groepl/Obsidian-Templates)























```cpp
#include <iostream>

int main() {
    int var = 20;
    int* ptr; // Declare an integer pointer

    ptr = &var; // Assign the address of 'var' to 'ptr'

    std==cout << "Value of var: " << var << std==endl;
    std==cout << "Address stored in ptr: " << ptr << std==endl;
    std==cout << "Value pointed to by ptr (*ptr): " << *ptr << std==endl;

    *ptr = 30; // Change the value at the address stored in ptr

    std==cout << "New value of var: " << var << std==endl;
    std==cout << "New value pointed to by ptr (*ptr): " << *ptr << std==endl;

    return 0;
}
```
*Original Answer:*
- The variable `ptr` has a value of `var` the ampersand operator is a reference operator meaning it points towards the pointer. (almost)
- This line prints out the value of the pointer. The (`*`) points to the pointer value meaning it will print the value instead of the address. (Correct)
- The original value of the `*ptr` is changed to 30. This means that the value of `var` which is being ponter to by the `*ptr` changes to 30. (Perfect)

1. What is happening on the line `ptr = &var;`? What does the `&` operator do?
	1. **Refinement:** You're very close! The `&` operator here is the "address-of" operator. So, `&var` gets the _memory address_ of the variable `var`. The line `ptr = &var;` means "assign the memory address of `var` to `ptr`." So, `ptr` doesn't store the _value_ of `var` (which is 20); it stores the _location_ in memory where `var`'s value is kept. You're right that it's about pointing, but it points to `var`'s address, not "towards the pointer" itself in this context.
2. What is happening on the line `std==cout << "Value pointed to by ptr (*ptr): " << *ptr << std==endl;`? What does the `*` operator (when used like this, `*ptr`) do?
	1. **Refinement:** This is a great explanation. The `*` operator, when used with a pointer like `*ptr`, is the "dereference" operator. It means "get the value stored at the memory address that `ptr` is holding/pointing to." So, if `ptr` holds the address of `var`, `*ptr` gets the value of `var`. You're spot on that it prints the value (20) instead of the address.
3. After `*ptr = 30;` is executed, why does the value of `var` also change?
	1. **Refinement:** Perfect! Because `ptr` holds the memory address of `var`, `*ptr = 30;` means "go to the memory location pointed to by `ptr` (which is `var`'s location) and change the value stored there to 30." Since `var` _is_ that memory location, its value changes.


---

