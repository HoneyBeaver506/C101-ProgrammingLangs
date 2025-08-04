---
Title: C++ Vector Container
tags:
  - type/note
  - type/sketchnote
  - programming/cpp
aliases:
  - Vector Containers
lead: Vectors are one of the collection types in C++
created:
  "{ DATE:YYYY-MM-DD, HH:mm }": 
modified:
  "{ DATE:YYYY-MM-DD, HH:mm }": 
template_type: Frontmatter
template_version: "1.12"
updated: 2025-06-06T14:25
---
# C++ Vectors
*Table of Contents:*
- [[#🎯 What & Why|🎯 What & Why]]
- [[#⚡ Core Syntax|⚡ Core Syntax]]
- [[#🔧 Essential Methods|🔧 Essential Methods]]
- [[#✏️ pictorial representation Visual Diagrams|✏️ pictorial representation Visual Diagrams]]
		- [[#Vector's `size` vs. `capacity`|Vector's `size` vs. `capacity`]]
- [[#⚖️ Quick Pros/Cons|⚖️ Quick Pros/Cons]]
- [[#🐛 Common Issues|🐛 Common Issues]]
- [[#💡 Key Tips|💡 Key Tips]]
- [[#❓Problems|❓Problems]]




## 🎯 What & Why
- In C++, `std::vector` is a sequence container from the Standard Template Library (STL) that provides a dynamic array.
    
- Unlike a traditional C-style array, a `std::vector` can automatically manage its storage, allowing it to grow and shrink in size at runtime.
    
- The elements are stored in a contiguous block of memory, which provides fast, constant-time random access to any element.



**Purpose & Use When:**
- `std::vector` is the default choice for most scenarios where you need a resizable array or a collection of objects.
    
- It is used when the number of elements is not known at compile time or when the collection needs to change size during program execution.
    
- Common use cases include:
    - Storing a list of records read from a file.
        
    - Creating a buffer for a resizable queue or stack.
        
    - Implementing algorithms that require fast access to elements by index.


**Analogy:**
- Think of a `std::vector` as a notebook with a flexible, expandable spine.
    
- You can start with a few blank pages (elements) and then add more pages at the end as you need them (`push_back`).
    
- If you run out of space, the notebook automatically gets a new, larger spine and all the pages are moved to a bigger notebook (`reallocation`).
    
- You can instantly flip to any page number (`O(1)` random access), but tearing out a page from the middle of the notebook requires you to manually shift all the subsequent pages forward (`O(n)` insertion/deletion).

## ⚡ Core Syntax
**Using `std::vector`**
To use `std::vector`, include the `<vector>` header:
```cpp
#include <vector>
```

**Declaration**
- **Basic declaration**  
  ```cpp
  std::vector<Type> name;
  ```

- **With an initial size**  
  ```cpp
  std::vector<int> scores(10); // A vector of 10 zeros
  ```

- **With a default value**  
  ```cpp
  std::vector<double> temps(5, 30.5); // A vector of 5 elements, all 30.5
  ```

**Initialization (since C++11)**
- **Using an initializer list**  
  ```cpp
  std::vector<int> numbers = {10, 20, 30, 40};
  ```

**Accessing Elements**
- **Using `operator[]`**  
  ```cpp
  int first_num = numbers[0]; // No bounds checking
  ```

- **Using `at()`**  
  ```cpp
  int second_num = numbers.at(1); // Throws std::out_of_range if index is invalid
  ```

**Adding Elements**
- **Add to the end**  
  ```cpp
  numbers.push_back(50);
  ```

**Iterating**
- **Using a range-based for loop (since C++11)**  
  ```cpp
  for (int num : numbers) {
      std::cout << num << " ";
  }
  ```

- **Using an iterator**  
  ```cpp
  for (auto it = numbers.begin(); it != numbers.end(); ++it) {
      std::cout << *it << " ";
  }
  ```



## 🔧 Essential Methods
 **Capacity and Size:**
- `size()`: Returns the number of elements currently in the vector.
        
- `capacity()`: Returns the total number of elements the vector can hold before needing to reallocate memory.
        
- `empty()`: Returns `true` if the vector contains no elements.
        
- `resize(n)`: Changes the number of elements to `n`. If `n` is smaller, elements are removed. If `n` is larger, new elements are added and value-initialized.
        
- `reserve(n)`: Requests that the vector's capacity be at least `n`. This is a crucial method for performance optimization to prevent reallocations.
        
- `shrink_to_fit()`: Reduces the capacity to match the current size (since C++11).
        
- **Element Access:**
- `front()`: Returns a reference to the first element.
        
- `back()`: Returns a reference to the last element.
        
- **Modifiers:**
- `push_back(value)`: Adds a new element to the end.
        
- `pop_back()`: Removes the last element.
        
- `insert(position, value)`: Inserts an element or range of elements at a specific position. This can be an expensive operation.
        
- `erase(position)`: Removes a single element or a range of elements. Also an expensive operation.
        
- `clear()`: Removes all elements from the vector, leaving the capacity unchanged.

## ✏️ pictorial representation Visual Diagrams
#### Vector's `size` vs. `capacity`
This diagram illustrates the distinction between a vector's `size` (the number of elements it contains) and its `capacity` (the total number of elements it can hold before a reallocation is needed).

```c++
// Initial Vector
std::vector<int> v;

// State: size=0, capacity=0
// Memory: []

// After v.push_back(10)
// State: size=1, capacity=1
// Memory: [10]

// After v.push_back(20) - Reallocation Occurs
// 1. New, larger memory block is allocated (e.g., capacity doubles)
// 2. Elements are copied over
// 3. Old memory is deallocated
// State: size=2, capacity=2 (or more, e.g., 4)
// Memory: [10, 20, <free>, <free>]

// After v.push_back(30)
// State: size=3, capacity=4
// Memory: [10, 20, 30, <free>]
```
**Explanation:** The `size` is the logical number of elements. The `capacity` is the physical memory allocated. When `size` equals `capacity`, the next `push_back` operation triggers a reallocation, which is an expensive process of copying all elements to a new memory location. This is why `reserve()` is so important.

## ⚖️ Quick Pros/Cons
*Advantages:*
- **Fast Random Access:** Due to its contiguous memory allocation, accessing any element by index is a constant-time operation (`O(1)`).
    
- **Dynamic Sizing:** `std::vector` can grow and shrink automatically, unlike C-style arrays.
    
- **Cache Friendliness:** Storing elements contiguously means that iterating over a `std::vector` is very fast, as elements are likely to be in the CPU's cache.
    
- **STL Compatibility:** `std::vector` integrates seamlessly with STL algorithms (e.g., `std::sort`, `std::find`).

*Disadvantages:*
- **Cost of Reallocation:** When the number of elements exceeds the current capacity, the vector must allocate a new, larger block of memory, copy all existing elements to the new location, and then deallocate the old block. This is an expensive operation (`O(n)`) that can introduce performance spikes.
    
- **Slow Middle Insertion/Deletion:** Inserting or removing an element in the middle of a `std::vector` requires shifting all subsequent elements, which is a linear-time operation (`O(n)`).
    
- **Iterator Invalidation:** After a reallocation, all iterators, pointers, and references to the old elements are invalidated. This is a common source of bugs.

## 🐛 Common Issues
- **Iterator and Reference Invalidation:** This is one of the most common and difficult-to-debug issues with vectors.
    
    - Any operation that can cause a reallocation (e.g., `push_back`, `insert`) will invalidate all existing iterators, pointers, and references.
        
    - Even `erase` and `insert` operations in the middle of the vector can invalidate some iterators and references, even without a reallocation.
        
    - **Solution:** After an operation that might invalidate iterators, always re-obtain the iterator, pointer, or reference.
        
- **Out-of-Bounds Access:**
    - Using `operator[]` on an invalid index (e.g., `vector[size()]`) leads to undefined behavior, which can be a crash, corrupted data, or seemingly random bugs.
        
    - **Solution:** Use `at()` for safer access with automatic bounds checking, especially when debugging. In performance-critical code, use `operator[]` but be sure to validate the index manually.
        
- **Performance Hit from Reallocation:**
    - Repeatedly calling `push_back` without pre-allocating can lead to numerous reallocations, which can significantly slow down your program.
        
    - **Solution:** Use `reserve()` to pre-allocate memory if you have a good estimate of the final size.

## 💡 Key Tips
- **Prefer `reserve()` over `resize()`:** Use `reserve()` to avoid reallocations. Use `resize()` when you want to change the number of active elements in the vector. `reserve()` only changes the capacity, while `resize()` changes both the size and capacity.
    
- **Pass `std::vector` by `const` Reference:** When passing a vector to a function, pass it as `const std::vector<T>&` to avoid creating an expensive copy of the entire vector. This is a crucial performance tip.
    
- **Use `emplace_back` for Complex Objects:** Use `emplace_back` instead of `push_back` when adding a complex object. `emplace_back` constructs the object in-place at the end of the vector, which can be more efficient by avoiding a copy or move operation.
    
- **Use Move Semantics:** When passing a vector by value, utilize move semantics (C++11+) by using `std::move` to transfer ownership efficiently. This avoids a deep copy of the vector's contents.
    
- **Use `vector::clear()` and `vector::shrink_to_fit()`:** If you need to empty a vector and reclaim its memory, call `clear()` followed by `shrink_to_fit()`. `clear()` alone only changes the size, not the capacity.


## ❓Problems
- **Basic**
    1. Create an `std::vector` of strings and add the names of three countries to it using `push_back`. Then, iterate through the vector using a range-based for loop and print each country name.
        
    2. Write a program that takes an integer `N` as input, then creates a vector of `N` integers and populates it with the numbers from 1 to `N`. Finally, print the first and last elements.
        
    3. Declare an `std::vector<double>` and initialize it with the values `1.1, 2.2, 3.3, 4.4, 5.5`. Use `v.at(2)` to access and print the third element, then use `v.pop_back()` to remove the last element and print the new last element.
        
- **Intermediate**
    1. Create a program that adds 1000 random integers to a vector. Before adding the elements, use `reserve()` to set the capacity to 1000. Measure the time it takes to add all the elements, then repeat the process without `reserve()` and compare the performance.
        
    2. Write a function `remove_duplicates` that takes a `std::vector<int>` by reference, removes all duplicate elements, and returns a new vector containing only the unique elements. Do not use STL algorithms like `std::unique`.
        
    3. Create a vector and add a few elements. Get an iterator to the first element. Then, add an element to the vector that causes a reallocation. Try to dereference the old iterator and explain why it causes a bug.
        
- **Advanced**
    1. Implement a function `merge_vectors` that takes two sorted `std::vector<int>`s and returns a new sorted vector containing all elements from both. Your solution should be more efficient than simply concatenating the vectors and then sorting the result.
        
    2. Create a class `Employee` with a constructor that takes a name and ID. Use an `std::vector<Employee>` and `emplace_back` to add new `Employee` objects to the vector. Compare the performance with `push_back` for a large number of employees and explain the difference.
        
    3. Write a function that takes a `std::vector<std::string>` and modifies it by removing all strings that start with the letter 'A'. The function must handle iterator invalidation correctly and should not create a new vector



---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on:: [[C++ Storage Data Types]]

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see:: [[C++ References & CheatSheets]]
