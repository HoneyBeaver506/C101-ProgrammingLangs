---
Title: Java Escape Sequences & Special Characters Cheat Sheet
Topic: Java Learning Curve
priority: Medium
status: Completed
tags:
  - type/note
  - programming/java
aliases: 
lead: Java Cheat Sheet with lead Characters
template_type: Note
template_version: "1.35"
updated: 2025-06-29T15:19
created: 2025-06-29T15:14
---
<!--  See "Template Help" below for using properties -->

# CS1 - Java Escape Sequences & Special Characters Cheat Sheet

**Table of Contents:**
- [[#1. Basic Escape Sequences|1. Basic Escape Sequences]]
	- [[#1. Basic Escape Sequences#1.1 Whitespace Characters|1.1 Whitespace Characters]]
	- [[#1. Basic Escape Sequences#1.2 Quote Characters|1.2 Quote Characters]]
	- [[#1. Basic Escape Sequences#1.3 Control Characters|1.3 Control Characters]]
- [[#2. Regex Metacharacters|2. Regex Metacharacters]]
	- [[#2. Regex Metacharacters#2.1 Character Classes|2.1 Character Classes]]
	- [[#2. Regex Metacharacters#2.2 Position Anchors|2.2 Position Anchors]]
	- [[#2. Regex Metacharacters#2.3 Special Regex Characters|2.3 Special Regex Characters]]
- [[#3. Unicode Escape Sequences|3. Unicode Escape Sequences]]
	- [[#3. Unicode Escape Sequences#3.1 Unicode Formats|3.1 Unicode Formats]]
	- [[#3. Unicode Escape Sequences#3.2 Common Unicode Characters|3.2 Common Unicode Characters]]
- [[#4. Printf Format Specifiers|4. Printf Format Specifiers]]
	- [[#4. Printf Format Specifiers#4.1 Basic Format Specifiers|4.1 Basic Format Specifiers]]
	- [[#4. Printf Format Specifiers#4.2 Format Modifiers|4.2 Format Modifiers]]
- [[#5. String Methods Reference|5. String Methods Reference]]
	- [[#5. String Methods Reference#5.1 String Manipulation Methods|5.1 String Manipulation Methods]]
	- [[#5. String Methods Reference#5.2 Character Testing Methods|5.2 Character Testing Methods]]
- [[#6. Common Use Cases|6. Common Use Cases]]
	- [[#6. Common Use Cases#6.1 File Path Handling|6.1 File Path Handling]]
	- [[#6. Common Use Cases#6.2 Data Parsing|6.2 Data Parsing]]
	- [[#6. Common Use Cases#6.3 Input Validation|6.3 Input Validation]]
	- [[#6. Common Use Cases#6.4 Text Formatting|6.4 Text Formatting]]
	- [[#6. Common Use Cases#6.5 Advanced Regex Examples|6.5 Advanced Regex Examples]]
- [[#Quick Reference Card|Quick Reference Card]]
	- [[#Quick Reference Card#Most Common Escape Sequences|Most Common Escape Sequences]]
	- [[#Quick Reference Card#Most Common Format Specifiers|Most Common Format Specifiers]]
	- [[#Quick Reference Card#Remember|Remember]]


## 1. Basic Escape Sequences

### 1.1 Whitespace Characters

|Sequence|Name|Definition|Use Case|Example|
|---|---|---|---|---|
|`\n`|Newline|Creates a new line|Line breaks in strings|`"Hello\nWorld"` → Hello<br>World|
|`\t`|Tab|Horizontal tab (8 spaces)|Indentation, alignment|`"Name:\tJohn"` → Name:        John|
|`\r`|Carriage Return|Returns cursor to line start|Windows line endings|`"Hello\r\nWorld"` (Windows format)|
|`\f`|Form Feed|Page break character|Printer control|`"Page1\fPage2"`|
|`\b`|Backspace|Moves cursor back one position|Cursor control|`"Hello\b World"`|
|`\`|Space|Literal space|When space might be ambiguous|`"word1\ word2"`|

### 1.2 Quote Characters

|Sequence|Name|Definition|Use Case|Example|
|---|---|---|---|---|
|`\"`|Double Quote|Literal double quote|Including quotes in strings|`"He said \"Hello\""` → He said "Hello"|
|`\'`|Single Quote|Literal single quote|Including apostrophes|`"It\'s working"` → It's working|
|`\\`|Backslash|Literal backslash|File paths, regex|`"C:\\Users\\John"` → C:\Users\John|

### 1.3 Control Characters

|Sequence|Name|Definition|Use Case|Example|
|---|---|---|---|---|
|`\0`|Null Character|ASCII 0|String termination|`"Hello\0"`|
|`\a`|Alert/Bell|ASCII 7|System beep|`"Alert!\a"`|
|`\v`|Vertical Tab|Vertical tabulation|Vertical alignment|`"Line1\vLine2"`|

---

## 2. Regex Metacharacters

### 2.1 Character Classes

|Sequence|Name|Definition|Matches|Example|
|---|---|---|---|---|
|`\d`|Digit|Any digit character|0-9|`"\\d+"` matches "123"|
|`\D`|Non-digit|Any non-digit character|Everything except 0-9|`"\\D+"` matches "abc"|
|`\w`|Word Character|Letters, digits, underscore|a-z, A-Z, 0-9, _|`"\\w+"` matches "hello_123"|
|`\W`|Non-word Character|Everything except word chars|Punctuation, spaces|`"\\W+"` matches "!@# "|
|`\s`|Whitespace|Any whitespace character|Space, tab, newline|`"\\s+"` matches "   \t\n"|
|`\S`|Non-whitespace|Any non-whitespace character|Visible characters|`"\\S+"` matches "hello!"|

### 2.2 Position Anchors

|Sequence|Name|Definition|Matches|Example|
|---|---|---|---|---|
|`\b`|Word Boundary|Position between word and non-word|Start/end of words|`"\\bcat\\b"` matches "cat" not "category"|
|`\B`|Non-word Boundary|Position not at word boundary|Inside words|`"\\Bcat\\B"` matches "cat" in "scattered"|
|`\A`|Start of String|Very beginning of string|String start|`"\\AHello"` matches start of "Hello World"|
|`\Z`|End of String|Very end of string|String end|`"World\\Z"` matches end of "Hello World"|

### 2.3 Special Regex Characters

|Sequence|Name|Definition|Use Case|Example|
|---|---|---|---|---|
|`\.`|Literal Dot|Matches actual dot character|File extensions|`"file\\.txt"` matches "file.txt"|
|`\*`|Literal Asterisk|Matches actual asterisk|Mathematical expressions|`"2\\*3"` matches "2*3"|
|`\+`|Literal Plus|Matches actual plus sign|Mathematical expressions|`"2\\+3"` matches "2+3"|
|`\?`|Literal Question Mark|Matches actual question mark|Sentences|`"Are you sure\\?"`|
|`\[`|Literal Left Bracket|Matches actual bracket|Array notation|`"arr\\[0\\]"` matches "arr[0]"|
|`\]`|Literal Right Bracket|Matches actual bracket|Array notation|Same as above|
|`\{`|Literal Left Brace|Matches actual brace|JSON, code|`"\\{key: value\\}"`|
|`\}`|Literal Right Brace|Matches actual brace|Same as above||
|`\(`|Literal Left Parenthesis|Matches actual parenthesis|Function calls|`"func\\(\\)"` matches "func()"|
|`\)`|Literal Right Parenthesis|Matches actual parenthesis|Same as above||
|`\|`|Literal Pipe|Matches actual pipe character|Command line|`"cmd1\|
|`\^`|Literal Caret|Matches actual caret|Exponents|`"2\\^3"` matches "2^3"|
|`\$`|Literal Dollar Sign|Matches actual dollar sign|Currency|`"\\$10"` matches "$10"|

---

## 3. Unicode Escape Sequences

### 3.1 Unicode Formats

|Format|Name|Definition|Range|Example|
|---|---|---|---|---|
|`\uXXXX`|Unicode 16-bit|4-digit hexadecimal|U+0000 to U+FFFF|`"\u0041"` → A|
|`\UXXXXXXXX`|Unicode 32-bit|8-digit hexadecimal|Full Unicode range|`"\U00000041"` → A|

### 3.2 Common Unicode Characters

|Character|Unicode|Escape|Description|
|---|---|---|---|
|©|U+00A9|`\u00A9`|Copyright symbol|
|®|U+00AE|`\u00AE`|Registered trademark|
|€|U+20AC|`\u20AC`|Euro symbol|
|™|U+2122|`\u2122`|Trademark symbol|
|→|U+2192|`\u2192`|Right arrow|
|←|U+2190|`\u2190`|Left arrow|
|↑|U+2191|`\u2191`|Up arrow|
|↓|U+2193|`\u2193`|Down arrow|
|★|U+2605|`\u2605`|Black star|
|☆|U+2606|`\u2606`|White star|

---

## 4. Printf Format Specifiers

### 4.1 Basic Format Specifiers

|Specifier|Type|Definition|Example Input|Example Output|
|---|---|---|---|---|
|`%d`|Integer|Decimal integer|`printf("%d", 42)`|42|
|`%f`|Float|Floating point|`printf("%.2f", 3.14159)`|3.14|
|`%s`|String|String|`printf("%s", "Hello")`|Hello|
|`%c`|Character|Single character|`printf("%c", 'A')`|A|
|`%b`|Boolean|Boolean value|`printf("%b", true)`|true|
|`%x`|Hexadecimal|Lowercase hex|`printf("%x", 255)`|ff|
|`%X`|Hexadecimal|Uppercase hex|`printf("%X", 255)`|FF|
|`%o`|Octal|Octal number|`printf("%o", 8)`|10|
|`%e`|Scientific|Scientific notation|`printf("%e", 1234.5)`|1.234500e+03|
|`%g`|General|Best of %f or %e|`printf("%g", 1234.5)`|1234.5|

### 4.2 Format Modifiers

|Modifier|Purpose|Example|Result|
|---|---|---|---|
|`%-10s`|Left-align in field|`printf("%-10s", "Hi")`|"Hi        "|
|`%10s`|Right-align in field|`printf("%10s", "Hi")`|"        Hi"|
|`%05d`|Zero-pad numbers|`printf("%05d", 42)`|"00042"|
|`%+d`|Show sign always|`printf("%+d", 42)`|"+42"|
|`% d`|Space for positive|`printf("% d", 42)`|" 42"|
|`%,d`|Use locale separators|`printf("%,d", 1000)`|"1,000"|

---

## 5. String Methods Reference

### 5.1 String Manipulation Methods

|Method|Purpose|Parameters|Return Type|Example|
|---|---|---|---|---|
|`split(regex)`|Split string by pattern|String regex|String[]|`"a,b,c".split(",")` → ["a","b","c"]|
|`replaceAll(regex, replacement)`|Replace all matches|String regex, String replacement|String|`"hello".replaceAll("l", "x")` → "hexxo"|
|`matches(regex)`|Test if string matches pattern|String regex|boolean|`"123".matches("\\d+")` → true|
|`contains(sequence)`|Check if contains substring|CharSequence|boolean|`"hello".contains("ell")` → true|
|`startsWith(prefix)`|Check if starts with string|String prefix|boolean|`"hello".startsWith("he")` → true|
|`endsWith(suffix)`|Check if ends with string|String suffix|boolean|`"hello".endsWith("lo")` → true|

### 5.2 Character Testing Methods

|Method|Purpose|Parameter|Return Type|Example|
|---|---|---|---|---|
|`Character.isDigit(ch)`|Test if character is digit|char|boolean|`Character.isDigit('5')` → true|
|`Character.isLetter(ch)`|Test if character is letter|char|boolean|`Character.isLetter('A')` → true|
|`Character.isWhitespace(ch)`|Test if character is whitespace|char|boolean|`Character.isWhitespace(' ')` → true|
|`Character.isUpperCase(ch)`|Test if character is uppercase|char|boolean|`Character.isUpperCase('A')` → true|
|`Character.isLowerCase(ch)`|Test if character is lowercase|char|boolean|`Character.isLowerCase('a')` → true|

---

## 6. Common Use Cases

### 6.1 File Path Handling

java

```java
// Windows paths
String windowsPath = "C:\\Users\\John\\Documents\\file.txt";

// Unix paths
String unixPath = "/home/john/documents/file.txt";

// Using forward slashes (works on both)
String universalPath = "files/data/input.txt";
```

### 6.2 Data Parsing

java

```java
// CSV parsing
String csvLine = "John,25,Engineer";
String[] parts = csvLine.split(",");

// Multi-delimiter parsing
String data = "apple;banana,orange:grape";
String[] fruits = data.split("[;,:]+");

// Whitespace splitting
String sentence = "Hello   world\t\nJava";
String[] words = sentence.split("\\s+");
```

### 6.3 Input Validation

java

```java
// Email validation (basic)
String email = "user@example.com";
boolean isValid = email.matches("\\w+@\\w+\\.\\w+");

// Phone number validation
String phone = "123-456-7890";
boolean validPhone = phone.matches("\\d{3}-\\d{3}-\\d{4}");

// Number validation
String input = "12345";
boolean isNumber = input.matches("\\d+");
```

### 6.4 Text Formatting

java

```java
// Pretty printing
System.out.printf("%s: %d points (%.1f%%)%n", name, score, percentage);

// Table formatting
System.out.printf("%-15s | %8s | %6s%n", "Name", "Score", "Grade");
System.out.printf("%-15s | %8d | %6s%n", "John Doe", 95, "A");

// Multi-line strings
String message = "Line 1\nLine 2\nLine 3";
String indented = "Item 1:\n\tDetail A\n\tDetail B";
```

### 6.5 Advanced Regex Examples

java

```java
// Extract all numbers from text
String text = "I have 5 apples and 3 oranges";
Pattern pattern = Pattern.compile("\\d+");
Matcher matcher = pattern.matcher(text);
// Results: "5", "3"

// Find words starting with capital letter
String sentence = "Hello World Java Programming";
String[] capitalWords = sentence.split("\\s+");
// Filter: words.matches("^[A-Z].*")

// Remove extra whitespace
String messy = "  Hello    world   ";
String clean = messy.trim().replaceAll("\\s+", " ");
// Result: "Hello world"
```

---

## Quick Reference Card

### Most Common Escape Sequences
- `\n` → New line
- `\t` → Tab
- `\"` → Quote
- `\\` → Backslash
- `\d` → Digit (regex)
- `\s` → Whitespace (regex)
- `\w` → Word character (regex)

### Most Common Format Specifiers
- `%d` → Integer
- `%s` → String
- `%f` → Float
- `%.2f` → Float with 2 decimals
- `%10s` → String in 10-character field

### Remember
- Use `\\` in Java strings for single `\` in regex
- Escape sequences work in strings, not in regex patterns directly
- Format specifiers are for `printf()`, `String.format()`, etc.
- Unicode escapes work in string literals


























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