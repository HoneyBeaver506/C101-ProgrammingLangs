---
Title: "202505281842"
Topic: CLang Learning Curve
tags:
  - programming/clang
  - type/note
  - type/sketchnote
aliases:
  - CBasics
Created At: Wednesday, May 28th 2025, 6:42:33 pm
Modified At: Tuesday, June 3rd 2025, 9:53:36 am
created: 2025-06-07T12:30
updated: 2025-06-07T18:39
---

# I. C++ Structures
Are user defined data types to group related variables of different types together under a single name. Structures are also known as *structs*. Structures are used to represent record.
- Gets its own separate memory location
- Takes up enough memory to hold its member simultaniously
- allows access at any time

*To define a Structure, you must use a struct Statement*
> [!Syntax] Syntax: Struct
> ```cpp
> struct [Structure Tag] {
> 	member definition;
> } [One or more structure variable];
> ```

The structure tag is optional. 
- Known simply as the identifier of the structure or name of the group of variables. The structure must end with the structure tag followed by a semicolon as below:
```cpp
struct Books { // Declaration of Blueprint
	char title[50]; // Member of the struct - [50] chars
	char author[50];
	char subject[100];
	int book_id; // Interger = Can hold a whole number
} book; // Instance Variable of Struct 'Books'

// Creation of Separate Instances
struct Books book1; // Creates a variable named 'book1' of type 'Books'.
struct Books book2; // Creates another variable named 'book2' of type 'Books'.
```
- Structure members can be accessed using the **member access Operator (.)** or dot operator. The member access operator is basically a period between the structure variable name and the structure member you wish to access. 

```cpp
   strcpy( Book2.author, "Yakit Singha"); // Example copy
   strcpy( Book2.subject, "Telecom");
   Book2.book_id = 6495700; // Accesing the ID
 
   // Print Book1 info
   cout << "Book 1 title : " << Book1.title <<endl;
   cout << "Book 1 author : " << Book1.author <<endl;
   cout << "Book 1 subject : " << Book1.subject <<endl;
   cout << "Book 1 id : " << Book1.book_id <<endl;

   // Print Book2 info
   cout << "Book 2 title : " << Book2.title <<endl;
   cout << "Book 2 author : " << Book2.author <<endl;
   cout << "Book 2 subject : " << Book2.subject <<endl;
   cout << "Book 2 id : " << Book2.book_id <<endl;

   return 0;
}
```

- `strcpy` → To access a string or char array, you need to copy these string of characters to access them and change their value. 
> [!Syntax] Syntax: STRUCT
> `strcpy(destination_array, source_text);`
- *Destination_array*: This is the char array within the struct. or the member of the structure.
- *Source_text*: This is the actual test you want to copy or move.

---
# Visuals and Diagrams

Let's visualize how the `Books` struct and its instances (`Book1`, `Book2`) store data in memory.

### Diagram 1: `struct Books` Blueprint

Imagine `struct Books` as a template or a cookie cutter. It defines the shape and slots for data, but it doesn't hold any actual data itself.

```
+-----------------+
|  struct Books   |
+-----------------+
| char title[50]  | <--- Slot for Title (text)
| char author[50] | <--- Slot for Author (text)
| char subject[100]| <--- Slot for Subject (text)
| int book_id     | <--- Slot for Book ID (whole number)
+-----------------+
```

- **`struct Books`**: This is the name of our blueprint.
- **`char title[50]`**: This box represents a space reserved for the book's title, which can be up to 49 characters long plus a special end marker.
- **`char author[50]`**: This box is for the author's name, similar in size to the title.
- **`char subject[100]`**: This box holds the subject of the book, allowing for more characters.
- **`int book_id`**: This box is for a numerical ID, a whole number.

### Diagram 2: `Book1` Instance with Data

When you declare `struct Books Book1;`, you create an actual "cookie" from the blueprint. This cookie has its own independent slots for data.

```
+------------------------+
|       Book1 (type Books)      |
+------------------------+
| title: "Learn C++..."  | <--- Contains the actual title
| author: "Chand Miyan"  | <--- Contains the actual author
| subject: "C++ Prog..." | <--- Contains the actual subject
| book_id: 6495407       | <--- Contains the actual ID
+------------------------+
```

- **`Book1 (type Books)`**: This represents the actual `Book1` variable.
- **`title: "Learn C++..."`**: This shows that the `title` member of `Book1` now holds the text "Learn C++ Programming".
- **`author: "Chand Miyan"`**: This shows the `author` member holds "Chand Miyan".
- **`subject: "C++ Prog..."`**: This shows the `subject` member holds "C++ Programming".
- **`book_id: 6495407`**: This shows the `book_id` member holds the number 6495407.

### Diagram 3: `Book2` Instance with Data

Similarly, `struct Books Book2;` creates another independent cookie.

```
+------------------------+
|       Book2 (type Books)      |
+------------------------+
| title: (uninitialized) | <--- This slot might be empty or hold random data if not set
| author: "Yakit Singha" | <--- Contains the actual author
| subject: "Telecom"     | <--- Contains the actual subject
| book_id: 6495700       | <--- Contains the actual ID
+------------------------+
```

- **`Book2 (type Books)`**: This represents the actual `Book2` variable.
- **`title: (uninitialized)`**: This highlights that the `title` for `Book2` was not explicitly set in the provided code snippet, so it might contain unexpected data.
- **`author: "Yakit Singha"`**: This shows the `author` member of `Book2` holds "Yakit Singha".
- **`subject: "Telecom"`**: This shows the `subject` member holds "Telecom".
- **`book_id: 6495700`**: This shows the `book_id` member holds the number 6495700.

These diagrams show how each instance of the `Books` struct has its own distinct set of data, even though they all follow the same structure defined by the `Books` blueprint

---
### Steps to follow
1. Declare the basic structure `struct` with its methods
2. Declare the structs variables. This is always necessary when developing a new structure instance. The struct statement above only creates the blueprint, and when declaring it, it creates the object.
3.  Assign values to the string methods with the `strcpy` statement
```cpp
strcpy(delcared_variable:method, "String to store");
```
4. Print the book information to test if the data was stored correctly.


---
# Pointers to Structures
> [!Syntax] Syntax: Pointers to Structures
> ```cpp
> // Development
> struct struct_name *struct_pointer;
> // Accessing Pointer
> struct_pointer = &struct_name
> // OR
> struct_pointer→title; // struct value
> ```

- Store the address of the structure into a pointer and use anywhere in the code.
- Makes memory usage more efficient and saves storage

---
**The Arrow Operator (→)**
Works perfectly when handling large amounts of data, and helps modify the original from any address.
—
Instead of using a dot operator to access a value from the structure, we use the arrow operator to point to the pointer. `struct_name->method`
```cpp
// Structure Access
(*bookPtr).title
// Structure Access with the ponter
bookPtr->title // More common
```

**Example:** If `bookPtr` points to `Book1`, then:
- `bookPtr->title` refers to `Book1`'s title.
- `bookPtr->author` refers to `Book1`'s author.
- `bookPtr->book_id` refers to `Book1`'s book ID.

*Function Prototype*:
```cpp
void prototype_name(struct struct_name *struct_pointer)

// Print Book1 info, passing address of structure 
prototype_name( &struct_name ); // Helps to pass only the address when the data is large.
```
- We want our `printBook` function to display `Book1`'s information. We use the `&` operator to get the memory address of `Book1` and pass that address (a pointer) to the `printBook` function.

## Visual Aids and Diagrams

Let's visualize how `printBook` works when you pass the address of a `struct`.

### Diagram 1: Before Calling `printBook(&Book1)`

Here's `Book1` in memory, holding its data.
![[C++. Structures 2025-06-07 17.53.40.excalidraw]]
### Diagram 2: Calling `printBook(&Book1)`

When you call `printBook(&Book1)`, the **address** of `Book1` (let's say it's Memory Address X) is passed to the `printBook` function. Inside `printBook`, the `book` parameter becomes a pointer holding this address.

![[C++. Structures 2025-06-07 17.28.25.excalidraw]]

- The arrow from `book` (inside `printBook`) to `Book1` indicates that the pointer `book` now "points to" or "references" the original `Book1` data in memory.
- When `printBook` uses `book->title`, it's essentially saying, "Go to the address I'm pointing to, and then find the `title` member there."


---
## Typedef 
A way of aliasing types
```cpp
typedef struct {
	char title[50];
	char author[50];
	char subject[100];
	int book_id;
} Books;
```
- Now you can use the Books structure directly without referencing the structure. 
- This also works with the pointer:
```cpp
typedef long int *pointer32;
pointer32 x,y,z
```

---
# II. Union

![[Pasted image 20250607182249.png]]
a union is a user-defined data type that allows you to store different data types in the same location.
- Can only store one of its member at a time
- The size of the union is determined by the larges member
- Limited to only taking one item at a time
- If you take one item, another member would replace it

*Analogy*: the `union` is one box. If you put an `int` (a small item) in it, it takes up a certain space. If you then put a `float` (another small item) in it, it uses the _same_ space, replacing the `int`. If you then put a `char` array (a larger item) in it, the box expands just enough to hold the `char` array, and the `int` or `float` are completely gone.

**To declare, use the `union` keyword + tag_name (`union_name`)**:
```cpp
union UnionName {
	dataType1 member1;
	dataType2 member2;
};
```
- To use the `union`, you need to declare its variable to access and manipulate is member
`union_name variable;`'
- To access the union member, you must use the (`.`)  operator after declaring a union variable.
`union_variable.member;`

---
### Union Steps
1. Define the union structure
```cpp
union Data {
  int intValue;       // Member for integer value
  float floatValue;   // Member for float value
  char strValue[50];  // Member for string value
}; // Semicolon is crucial here!
```
2. Define the main Function and declare the `Union` blueprint
```cpp
int main() {
  // Defining (Initializing) a union variable
  Data data;
  // ... rest of main function ...
  return 0;
}
```
3. Assign the values and then print them
```cpp
data.intValue = 2006;
```
4. Assign the value to the second (Overwrites, Erases initial)
```cpp
data.floatValue 5.57F;
```

![[C++. Structures 2025-06-07 18.30.09.excalidraw]]
- Once the member is overwritten, it cannot be accessed. Always access a most recently written member.

 **Mistake:** Forgetting that previous data is overwritten.
- **Why it happens:** While explicit "clearing" isn't usually necessary because assignment overwrites, a deeper understanding of how `union`s work reminds you that whatever was there before is gone once you assign to a different member.
- **Solution:** Consciously consider which member is "active" at any given moment. Only access that active member.
- **Prevention:** Use a separate "tag" or "discriminator" variable (often an `enum` or `int`) alongside your `union` to keep track of which member is currently valid. This is a common pattern for "safe" union usage.


**Mistake:** Assuming a `union` is the sum of its members' sizes.
- **Why it happens:** Beginners often confuse `union`s with `struct`s regarding memory allocation.
- **Solution:** Recall that a `union` allocates memory equal to the size of its _largest_ member. You can verify this using `sizeof(Data)` in your program.
- **Prevention:** When thinking about `union`s, always visualize the shared memory space.









---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on::

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see:: [[C++ Storage Data Types]]

**Terms**
<!-- Links to definition pages. -->
-  [[D1 - Terms & Definitions]]

**Target**
<!-- Link to project note or externaly published content. -->
- used_in::

---
