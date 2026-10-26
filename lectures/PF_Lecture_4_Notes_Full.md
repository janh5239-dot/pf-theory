# PF Lecture 4: Variables and Data Types

**Source:** Mod_PF_Lec_4_Sp_2026 (PDF, 36 pages)
**Instructor:** Engr. Dr. Alauddin
**Topic:** Programming fundamentals

**Legend**
- *Printed:* text from the original slide
- **[Handwritten]:** red, blue, or black ink added by the lecturer
- **[Diagram]:** drawn figure, table, or memory map
- **[Uncertain]:** handwriting that is hard to read; the most likely meaning is given
- **[Note]:** a possible error or inconsistency in the slide itself

---

## Table of Contents

1. Title and roadmap (Slides 1 to 2)
2. Character set (Slides 3 to 4)
3. Building blocks: constants, variables, keywords, identifiers (Slides 5 to 15)
4. Variables in memory (Slides 16 to 17)
5. Declaration of variables (Slides 18 to 21, 19)
6. Initialization and assignment (Slides 22 to 26)
7. Fundamental data types (Slide 27)
8. Memory maps and bits (Slides 24, 28 to 31)
9. The cout statement and expressions (Slides 32 to 35)
10. Summary

---

## 1. Title and Roadmap

### Slide 1: Title
- *Variables and Data Types*, Lecture 4 (Programming fundamentals), by Engr. Dr. Alauddin.

### Slide 2: Steps in Learning C++
*[Diagram: flow of four boxes]*
**Alphabets, Digits, Special symbols → Constants, Variables, Keywords → Instructions → Program**

*Printed table, Character set:*

| Category | Members |
|---|---|
| Alphabets | A, B, …, Y, Z and a, b, …, y, z |
| Digits | 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 |
| Special symbols | ~ ‘ ! @ # % ^ & * ( ) _ - + = | \ { } [ ] : ; " ' < > , . ? / |

*Handwritten:* none.

---

## 2. Character Set

### Slide 3: Character Set
*Printed:*
1. The character set is the collection of valid symbols in C++.
2. Alphabets are part of the character set.
3. Digits from 0 to 9 are used to create numeric constants.
4. Symbols such as `+`, `-`, `{}`, `()`, and `;` perform specific programming functions.

*Handwritten:* none.

### Slide 4: Character Set (contd.)
*Printed:*
- Whitespace characters separate program elements. Spaces, tabs, and new lines improve readability but generally do not affect execution.
- Escape sequences represent special characters, for example `\n` (new line) and `\t` (horizontal tab).

*Handwritten:* none.

---

## 3. Building Blocks of C++

### Slide 5: Important Building Blocks
*Printed:*
1. Constants
2. Variables
3. Keywords
4. Identifiers

*Handwritten:* none.

### Slide 6: Constants (types)
*Printed:*
- A **constant** is a fixed value. Once defined, its value does not change during program execution.
- **Types:**
  - **i. Integer constants:** whole numbers with no decimal point, for example `25`, `-150`, `1000`.
  - **ii. Real (floating-point) constants:** decimal numbers, for example `3.14`, `0.5`, `-8.75`. Common in scientific and engineering calculations.

*Handwritten:* none.

### Slide 7: Constants (contd.)
*Printed:*
- **iii. Character constants:** represent a single character, enclosed in single quotation marks, for example `'A'`, `'9'`, `'#'`.

*Handwritten:* none.

### Slide 8: Variables
*Printed:*
- A **variable** is a named location in the computer's memory that stores data.
- Every variable has:
  - a unique **name**,
  - a **data type**, and
  - a **value**, which may or may not change during program execution.
- Every variable also has an **address** in memory.

*Handwritten:* none.

### Slide 9: Rules for Variable Names
*Printed:*
1. A variable name is a series of characters made of letters, digits, and underscores (`_`).
2. It must not begin with a digit.
3. C++ is **case sensitive**. `a2` and `A2` are different variables.
4. Do not begin names with an underscore or double underscore, because the compiler may use such names internally.
5. You cannot use a C++ keyword as a variable name.

*Handwritten:* none.

### Slide 10: Keywords
*Printed:*
- **Keywords** are reserved words with a predefined meaning in the C++ language.
- The compiler recognizes them as part of C++ syntax.
- Keywords cannot be used as variable names, function names, or other user-defined identifiers.
- Examples: `int`, `double`, `char`, `if`, `else`, `for`, `while`, `return`.

*Handwritten:* none.

### Slide 11: Keywords (contd.)
*Printed:*
- `int`, `double`, and `char` are keywords that specify fundamental data types.
- C++ is case sensitive, so keywords must be written with their exact spelling. `int` is a keyword, but `Int` and `INT` are not.
- Keywords are not in any namespace, because they are part of the language itself, not something declared by a header.

*Handwritten:* none.

### Slide 12: Identifiers
*Printed:*
- An **identifier** is a name chosen by a programmer (or by the library) for something: a variable, function, class, namespace, and so on.
- `main`, `cout`, `cin`, and `std` are not keywords, so they are ordinary identifiers.
- Identifiers can be used as variable names.

*Handwritten:* none.

### Slide 13: Keyword vs Identifier vs Variable
*Printed:*

| Term | Meaning |
|---|---|
| Keyword | A word with a fixed meaning built into the language. You cannot use it as a variable name. |
| Identifier | A name chosen by a programmer (or the library) for a variable, function, class, namespace, etc. |
| Variable | A named place in memory that stores a value. |

*Handwritten:* none.

### Slide 14: Keyword vs Identifier vs Variable (example)
*Printed code:*
```cpp
#include <iostream>
using namespace std;

int main()
{
    int age = 20;
    cout << "My age is" << age;
}
```
*Printed notes:*
- Keywords in this program: `using`, `namespace`, `int`. They are always lowercase and cannot be used as names.
- Identifiers: `main` (function name), `age` (variable name), `std` (namespace name), `cout` (object name). None of these are keywords.
- Variable: `age`.

*Output:* `My age is20`, because the text is printed with no space before the number.

*[Note]:* the quotation marks in the printed code are curly (“ ”). C++ requires straight quotes (" "). Copied exactly, the code will not compile.

*Handwritten:* none.

### Slide 15: How They Relate
*Printed:*
- Keywords are reserved words, so they are never used as identifiers or variable names.
- Every variable name is an identifier, but not every identifier is a variable.
  - `main` is a function name, and `std` is a namespace name. Both are identifiers, not variables.

*Handwritten:* none.

---

## 4. Variables in Memory

### Slide 16: Important Points about Variables (memory map)
*[Diagram: memory map, handwritten]*
- **Declaration:** `int abc;` in source code. It takes **4 bytes**.
- **Memory (RAM):** a box containing the name `abc`, the value `3`, and the address `3497H` (hexadecimal).
- Labels with arrows:
  - **Name of the variable:** `abc`
  - **Value inside / stored (of type int):** `3`
  - **Address:** `3497H`
- The 4-byte block is marked with a bracket.
- **Initialization:** `int abc = 3;`, with a bracket around the whole statement.

*Handwritten:* all of the above, with highlights in yellow and cyan.

### Slide 17: A Simplified View of a Local Variable in Program Memory
*[Diagram: program memory layout]*
- The layout shows four regions of program memory, from top to bottom:
  1. **Program code:** instructions
  2. **Static data:** long-lived data
  3. **Heap:** dynamic data, studied later
  4. **Stack:** local variables and function calls
- A zoom arrow points to the **Stack**.
- The heading "Where does a local variable go?" sits beside the diagram.

*Handwritten:* a check mark beside the stack, the word **"Stack"** at the top right, and a small box labelled **"var…"** (probably "variable") inside a larger box, to show a local variable inside the stack.

---

## 5. Declaration of Variables

### Slide 18: Declaration
*Printed:*
- During declaration, the programmer specifies the variable's data type so the compiler can allocate the correct amount of memory.
- Syntax: `Datatype variable_name;`
- Example: `int books;`, where `int` is the data type (a whole number) and `books` is the variable name.
- Declarations can be placed almost anywhere in a program, but they must appear **before** the variable is used.

*Handwritten:* none.

### Slide 19: Declaration Placement (C vs C++)
*[Diagram: handwritten code fragments]*
- Heading in the top right: **"C++"**.
- Left side, a block labelled **{ int a, b, c; … }**, with an arrow to the letter **"C"**. The note means that C requires declarations at the start of a block.
- Right side, a block **{ a = b + c; int a, b, c; }**, with the second line crossed out and an arrow. This code is not allowed in C.
- Bottom notes:
  - **"* first declaration then use it"**
  - **"* Anywhere"**
- Meaning: in C, all declarations must come first in a block. In C++, a declaration can appear anywhere, as long as it comes before the variable is used.

*Printed:* none.

### Slide 20: Declaration of Variables (contd.)
*Printed:*
- Several variables of the same type may be declared in one declaration or in several.
- **Case 1, multiple declarations:**
  ```cpp
  int number1;
  int number2;
  int sum;
  ```
- **Case 2, one comma-separated declaration:**
  ```cpp
  int number1, number2, sum;
  ```

*Handwritten:* none.

### Slide 21: More Declaration Examples
*Printed:*
- Integers, floating-point numbers, and characters are stored in variables of the appropriate data types.
  ```cpp
  int bas;
  float rs, grosssal;
  char name, code;
  ```
- Character constants are stored in character variables.

*Handwritten:* none.

---

## 6. Initialization and Assignment

### Slide 22: Initializing a Variable
*Printed:*
- **Initialization:** assigning a value to a variable.
- The variable name goes on the left of the assignment operator `=`. Expressions (variables and constants) go on the right.
- Examples:
  ```cpp
  int abc = 5;          // assign a value
  c = b + a;            // add two values, assign to a third variable
  int i = 10, j = 25;   // initialize several variables on one line
  float a = 1.5, b = 1.99 + 2.4 * 1.44;
  ```

*Handwritten:* none.

### Slide 23: Assignment Rules (handwritten)
*[Handwritten examples with check marks and cross marks]*
- ✓ `a = 5;`
- ✓ `a = b;`
- ✓ `a = a + 5;`, with an arrow showing the value of `a` on the right flowing back into `a`.
- ✓ `a = 2 * a;`
- ✗ `2 * a = b`, crossed out.
- Note: **"Always single variable on left-side of ="**

*Printed:* none.

### Slide 24: Memory Map (handwritten code and memory)
*[Handwritten code and memory map]*
```cpp
int main()
{
    int a;
    float b;
    a = 3;
    b = 2.5;
    cout << a;
    cout << b;
}
```
- Memory map: variable `a` holds `3`, and variable `b` holds `2.5`.
- **Output:** `32.5`. There is no `endl`, so the two values appear on the same line.
- Note beside the output: "// display value of…" [Uncertain: the comment is cut off at the edge of the slide].

### Slide 25: Initializing a Variable (contd.)
*Printed:*
- Only one variable may be on the left-hand side of the assignment operator `=`.
- `z = k * l` is legal, but `k * l = z` is illegal.
- The variables and constants together are called **operands**, which are acted on by **operators**.

*Handwritten:* none.

### Slide 26: Assigning Character Constants to Character Variables
*Printed:*
```cpp
char a, b, d;
a = 'F';
b = '8';
d = '+';
```
- The ASCII values of the characters are stored in the variables.
- ASCII values are used to represent any character in memory.
- The ASCII values of `'F'` and `'8'` are given as **70** and **38**.

*[Note]:* the ASCII value of `'8'` is **56** (decimal), not 38. The value 38 is the ASCII code for `&`. The value for `'F'` (70) is correct.

*Handwritten:* none.

---

## 7. Data Types

### Slide 27: Common Fundamental C++ Data Types
*Printed table:*

| Data type | Data stored | Common size* | Example | Important observation |
|---|---|---|---|---|
| `bool` | Logical value | 1 byte | `true` | Usually displayed as 1 or 0. |
| `char` | One character or a small integer | 1 byte | `'A'` | A character literal uses single quotation marks. |
| `short` | Small whole number | 2 bytes | `1200` | Its guaranteed range is smaller than or equal to `int`. |
| `int` | Whole number | 4 bytes | `45000` | The usual choice for ordinary whole numbers. |
| `long` | Whole number | 4 or 8 bytes | `120000L` | Its size varies across platforms. |
| `long long` | Large whole number | 8 bytes | `9000000000LL` | Useful when `int` may not hold the required range. |
| `float` | Decimal value, lower precision | 4 bytes | `3.14f` | The `f` suffix makes the literal a `float`. |
| `double` | Decimal value, higher precision | 8 bytes | `3.14159` | The usual choice for measured or calculated values. |
| `long double` | Extended precision | 8, 12, or 16 bytes | `3.14159L` | Size and precision depend on the platform. |

\* Sizes are typical and may vary by platform.

*Handwritten:* none.

---

## 8. Bits, Memory, and Value Ranges

These slides have handwriting that works out how many values a variable can hold, based on how many bits it reserves.

### Slide 28: Space Reserved as Bits
*[Handwritten]*
- **"Space reserved is 1-bit."** The variable `n` gives the number of bits.
- **Possible values to be stored:**

  | Binary | Decimal |
  |---|---|
  | 0 | 0 |
  | 1 | 1 |

- **"You can store max 2 values (0 or 1)."**
- **Formula:** `2^n = 2^1 = 2`, where `n` is the length of the bit string. So 2 numbers can be stored.
- A diagram of a memory cell, drawn as a box.
- **"Max value that can be stored (2^n − 1)"** is written at the bottom. [Uncertain: the right side is cut off, so the full expression is not visible.]

### Slide 29: Two-Bit Example
*[Handwritten]*
- **"2-bits ⇒ n."** A box with 2 bits is drawn.
- Table:

  | Binary | Decimal |
  |---|---|
  | 0 0 | 0 |
  | 0 1 | 1 |
  | 1 0 | 2 |
  | 1 1 | 3 |

- **"It can store"** the values in the table.
- **Total values = 4.** Using the formula: `2^n = 2^2 = 4`.
- **"a has 2-bit reserved."** Arrow from the variable `a`.
- Example check: `int a = 3;` ✓. `a = 4;` ✗ (crossed out), because 4 needs 3 bits.
- Note: "For example, a machine reserves two bits for int ⇒ `int a;`". This is a teaching example, not a real machine. In real systems, `int` is 4 bytes.

### Slide 30: Eight-Bit and 32-Bit Ranges
*[Handwritten]*
- **"Let 8 bits (1 byte is reserved)"** for `int abc;`. Written as `int abc;` with "Let size = 1 byte."
- **Total number of values that can be stored:** `2^8 = 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 = 256`.
- The values run from **0 to 255**.
- **abc = 255** ✓, and **abc = 256** ✗ (crossed out).
- **"What will be the last/max value that can be stored?"**
- **For `int` (4 bytes = 32 bits):** `2^32 = 4294967296`, so the values run from **0 to 4294967295**. [Uncertain: the last digit is partly crossed out, but the calculation is correct.]

### Slide 31: First and Last Values in 32 Bits
*[Handwritten]*
- **"2^32 = first value"**, shown as `00…00` (thirty-two zeros). A bracket labels the group as a **32-bit** value.
- **"Last value / Max value"**, shown as `11…11` (thirty-two ones). A bracket labels it **"32 1's"**.
- The label **"(255)"** is written next to the 32 ones. [Note: this is inconsistent. 255 is the maximum value of 8 bits (eight ones). The maximum value of 32 bits is 4294967295. The "(255)" label probably belongs to the 8-bit example on the previous slide and was written here by mistake.]

---

## 9. The cout Statement and Expressions

### Slide 32: Important Points about cout
*Printed:*
- `cout` not only prints character strings. It can also print the result of an **expression**.
- An expression is a valid combination of constants, variables, and operators.
- Examples of valid expressions: `3`, `3 + 2`, `c`, and `a + b * c - d`.
- The results of these expressions can be printed, as shown on the next slide.

*Handwritten:* none.

### Slide 33: Program 2 (use of cout)
*Printed code:*
```cpp
// This program is written just to show the use of cout
#include <iostream>
using namespace std;

int main()
{
    int a = 10, b = 5, c = 2, d = 3;

    cout << 3 << endl;
    cout << 3 + 2 << endl;
    cout << c << endl;
    cout << a + b * c - d << endl;
}
```
*Printed question:* "O/P?? And Memory map ??"

*Working out the output:*
- `3` → `3`
- `3 + 2` → `5`
- `c` → `2`
- `a + b * c - d` → `10 + 5 × 2 − 3` = `17`

**Output:**
```
3
5
2
17
```

*Handwritten:* none. The answer is left for the student to work out.

### Slide 34: Program 3 (addition of two integers)
*Printed code:*
```cpp
#include <iostream>
using namespace std;

int main()
{
    int a = 10, b = 5, c;   // initialization at the time of declaration
    c = b + a;
    cout << c << endl;
    cout << "answer is" << 3 + 2 << endl;
    cout << "answer is" << c << endl;
    cout << a + b * c << endl;
}
```

*Working out the output:*
- `c = b + a` → `c = 15`
- `cout << c` → `15`
- `cout << "answer is" << 3 + 2` → `answer is5`
- `cout << "answer is" << c` → `answer is15`
- `cout << a + b * c` → `10 + 5 × 15` = `85`

**Output:**
```
15
answer is5
answer is15
85
```

*[Note]:* the slide uses curly quotation marks (“answer is”) in the `cout` lines. Straight quotes are required, so the code will not compile as printed. The comment also contains a spelling error, "initilization."

*Handwritten:* none.

### Slide 35: Program with Two Output Strings (handwritten)
*[Handwritten code]*
```cpp
{
    int a = 2, b = 3;
    cout << "value of b is" << a;
    cout << "value of a is" << b;
}
```
- Output written beside the code: **"value of b is 2"** and **"value of a is 3"**.
- The printed text is the string in quotes, and the number is the value of the variable after `<<`. The label "value of b is" is followed by `a`, so the number shown is the value of `a`, not `b`. The output therefore reads as written, and the label does not describe the value that follows it.

*Note:* the handwritten output has a space between the label and the number. As written in the code, the string has no trailing space, so the output would be `value of b is2` unless a space is added.

### Slide 36: (blank)
*[Diagram: blank slide with the theme]*
- No content.

---

## 10. Summary

1. **Character set:** letters, digits, and special symbols are the basic characters of C++.
2. **Building blocks:** constants (fixed values), variables (named memory), keywords (reserved words), and identifiers (programmer names).
3. **Constants:** integer, real (floating-point), and character constants.
4. **Variables:** a name, a data type, a value, and an address. Names must start with a letter or underscore, and C++ is case sensitive.
5. **Declaration:** `Datatype name;`, placed before use. Several variables may be declared in one line, separated by commas.
6. **Initialization:** `name = value;`. Only one variable may appear on the left of `=`.
7. **Data types:** `bool`, `char`, `short`, `int`, `long`, `long long`, `float`, `double`, and `long double`. Each has a typical size.
8. **Range of values:** an n-bit variable can hold 2^n values. An 8-bit value runs from 0 to 255. A 32-bit value runs from 0 to 4294967295 when all bits are used as unsigned values; the slides do not discuss signed ranges.
9. **cout:** prints strings and expressions. Expressions are combinations of constants, variables, and operators.

---

## Notes on Uncertain Items and Errors in the Slides
- Slide 14, and the printed code on Slide 34: curly quotation marks, which will not compile. Use straight quotes.
- Slide 26: the ASCII value of `'8'` is **56**, not 38.
- Slide 31: the label "(255)" next to 32 ones should not be there. The 32-bit maximum is 4294967295.
- Slide 24: the comment beside the output is cut off at the edge of the slide.
- Slide 28: the bottom expression is cut off at the edge of the slide.
- Slide 30: the last digit of the 32-bit value is partly crossed out, but the calculation is correct.
- Slide 34: the comment contains the spelling error "initilization."
