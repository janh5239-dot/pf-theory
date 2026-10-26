# PF Lecture 5: Programming Basics (Output, Input, and Operators)

**Source:** Mod_PF_Lec_5_Sp_2026 (PDF, 25 pages)
**Instructor:** Engr. Dr. Alauddin
**Topic:** Programming fundamentals

**Legend**
- *Printed:* text or table from the original slide
- **[Handwritten]:** red or black ink added by the lecturer
- **[Diagram]:** drawn figure or table
- **[Uncertain]:** handwriting that is hard to read; the most likely meaning is given
- **[Note]:** a possible error or inconsistency in the slide
- **[Added]:** a teaching point added by these notes, not on the slide

---

## Table of Contents

1. Title (Slide 1)
2. Printing with multiple lines (Slide 2)
3. Storing values without cin (Slides 3 to 4)
4. Reading values with cin (Slide 5)
5. Arithmetic operators and the modulus operator (Slides 6 to 9)
6. Parentheses and precedence (Slides 10 to 15)
7. Assignment and compound operators (Slides 16 to 17)
8. Increment and decrement operators (Slides 18 to 21)
9. Input example and exercises (Slides 22 to 25)
10. Summary

---

## 1. Title

### Slide 1: Title
- *Programming basics*, Lecture 5 (Programming fundamentals), by Engr. Dr. Alauddin.

---

## 2. Printing Multiple Lines

### Slide 2: Example (multiple lines with one statement)
*Printed code:*
```cpp
// Printing multiple lines of text with a single statement.
#include <iostream> // enables program to output data to the screen

// function main begins program execution
int main()
{
    std::cout << "Welcome\n to \n\nC++!\n";
} // end function main
```

*Printed output:*
```
Welcome
to

C++!
```

*What the code does:* the escape sequence `\n` starts a new line. `\n\n` gives one blank line. Each `\n` moves to the next line, so one statement prints four lines.

*[Note]:* the code prints `" to "` with a leading space, so the second output line is ` to ` with one space before the word. The printed output shows `to` with no space. The output on the slide is therefore slightly different from what the code produces.

*Handwritten:* none.

---

## 3. Program Without cin

### Slide 3: Program without using cin
*Printed:*
- Stores the values of one student's name, the number of labs submitted, and the average marks.

*Handwritten:* none.

### Slide 4: Storing and displaying values (no cin)
*Printed code:*
```cpp
#include <iostream>
#include <string>
using namespace std;

int main()
{
    string studentName = "abc";
    int completeedLabs = 8;     // note the spelling
    double averageMark = 90.0;
    cout << "Student: " << studentName << endl;
    cout << "Progress: " << completedLabs << " labs, average "
         << averageMark << endl;
    return 0;
}
```

*Output (from the code, after correcting the spelling):*
```
Student: abc
Progress: 8 labs, average 90
```

*Key points:*
- `string` is a type from the `<string>` header.
- `endl` moves the output to a new line. It is the same as `"\n"` for this purpose.
- A `double` value of `90.0` prints as `90`, because C++ does not print trailing zeros.

*[Note]:* the code declares `completeedLabs` (with an extra "e") but prints `completedLabs`. This is a compile error. The two names must match exactly, because C++ is case sensitive and every name must be spelled the same way each time it is used.

*Handwritten:* none.

---

## 4. Reading Values with cin

### Slide 5: Reading values with cin
*Printed code:*
```cpp
#include <iostream>
#include <string>
using namespace std;

int main()
{
    string studentName;
    int completedLabs;
    double averageMark;

    cout << "Enter first name: ";
    cin >> studentName;
    cout << "Enter completed labs: ";
    cin >> completedLabs;
    cout << "Enter average mark: ";
    cin >> averageMark;

    cout << "Student: " << studentName << endl;
    cout << "Progress: " << completedLabs << " labs, average "
         << averageMark << endl;
    return 0;
}
```

*How it works:*
- `cin >> variable` reads a value typed by the user and stores it in the variable.
- The prompts (`cout << "Enter ..."`) tell the user what to type.
- The variables are declared first, and then the values are read into them.

*Example run (user input in bold in the explanation, not shown on the slide):*
```
Enter first name: Ali
Enter completed labs: 8
Enter average mark: 90
Student: Ali
Progress: 8 labs, average 90
```

*[Added]:* `cin >> studentName` reads only one word. A name with a space, such as "Ali Khan," would be split. Reading a full line needs `getline`, which is not covered on these slides.

*Handwritten:* none.

---

## 5. Arithmetic Operators

### Slide 6: Arithmetic and arithmetic operators (table)
*[Diagram: table, with handwriting]*

| C++ operation | C++ arithmetic operator | Algebraic expression | C++ expression |
|---|---|---|---|
| Addition | `+` | f + 7 | `f + 7` |
| Subtraction | `-` | p − c | `p - c` |
| Multiplication | `*` | bm or b · m | `b * m` |
| Division | `/` | x/y or x÷y | `x / y` |
| Modulus | `%` | r mod s | `r % s` |

**[Handwritten]**
- Red arrow pointing at the **Algebraic expression** column, labelled **"Mathematic books."** This column shows how mathematics textbooks write the expressions.
- Red check mark beside the **C++ expression** column. This is the column to use in C++ code.

### Slide 7: Arithmetic operators (contd.)
*Printed:*
- The asterisk `*` means multiplication, and the percent sign `%` is the modulus operator. Neither is used in linear algebra.
- The operators in the table are all **binary operators**, which take two operands.
- Example: in `number1 + number2`, the binary operator is `+`, and the operands are `number1` and `number2`.

*Handwritten:* none.

### Slide 8: The modulus operator
*Printed:*
- C++ provides the **modulus operator** `%`, which gives the remainder after integer division.
- The modulus operator can be used **only with integer operands**.
- The expression `x % y` gives the remainder when `x` is divided by `y`.
- Examples: `7 % 4` gives `3`, and `17 % 5` gives `2`.

*Handwritten:* none.

### Slide 9: Working out the modulus by long division
*[Handwritten]*
- **7 % 4 = 3:** long division of 7 by 4 gives quotient 1 and remainder 3. An arrow points from the remainder to the answer.
- **8 % 4 = 0:** 4 goes into 8 twice, with no remainder.
- **4 % 7 = 4:** 7 goes into 4 zero times, so the remainder is 4.
- **3 % 7 = 3:** 7 goes into 3 zero times, so the remainder is 3.
- **Rule written at the bottom:** *"If on the left side of %, the value is smaller than that value, then that value will be the answer."* In other words, when the left operand is smaller than the right one, the result is the left operand.

*[Added]:* the modulus of a negative number is not covered on the slides. Its sign depends on the C++ standard version, so it should not be used without checking.

---

## 6. Parentheses and Precedence

### Slide 10: Parentheses
*Printed:*
- Parentheses are used in C++ expressions in the same way as in algebra.
- Example: to multiply `a` by `(b + c)`, write `a * ( b + c )`.

*Handwritten:* none.

### Slide 11: Order of evaluation with parentheses
*Printed:*
- Operators inside a pair of parentheses are evaluated first. Parentheses are said to have the "highest level of precedence."
- For nested (embedded) parentheses, such as `(a * (b + c))`, the operators in the innermost pair are applied first.

*Handwritten:* none.

### Slide 12: Precedence table
*[Diagram: table]*

| Operator(s) | Operation(s) | Order of evaluation (precedence) |
|---|---|---|
| `( )` | Parentheses | Evaluated first. If nested, the innermost pair is evaluated first. |
| `*`, `/`, `%` | Multiplication, division, modulus | Evaluated second. If there are several, they are evaluated left to right. |
| `+`, `-` | Addition, subtraction | Evaluated last. If there are several, they are evaluated left to right. |

*Printed caution:* in an expression such as `(a + b) * (c - d)`, where two sets of parentheses are not nested but appear on the same level, the C++ standard does **not** specify which one is evaluated first.

*Handwritten:* none.

### Slide 13: Algebra and C++ formulas
*[Diagram: two rows, with handwriting]*
- **Algebra:** `m = (a + b + c + d + e) / 5`
  **C++:** `m = ( a + b + c + d + e ) / 5;`
- **Algebra:** `y = mx + b`
  **C++:** `y = m * x + b;`

**[Handwritten]**
- Under the first row, a corrected version with a cross mark: **"m = a + b + c + d + e/5;"** with an **X** beside it. This line is wrong. Without parentheses, the `/` applies only to `e`, so it does not divide the sum by 5.
- *Explanation:* parentheses are needed around the sum so that the division applies to the whole sum.

### Slide 14: Evaluation order with step numbers
*[Diagram: C++ statement with steps]*
- **Statement:** `z = p * r % q + w / x - y;`
- **Step numbers under each operator:**
  - Step 1: `*` (p × r)
  - Step 2: `%` (result of step 1 mod q)
  - Step 3: `/` (w ÷ x)
  - Step 4: `+` (add step 2 to step 3)
  - Step 5: `-` (subtract y)
  - Step 6: `=` (assign the result to z)

**[Handwritten]**
- A red bracket above the expression labelled **"answer."**
- A red bracket below the steps labelled **"step nos."**
- Written at the bottom: **"Assignment of the answer to the variable z is the last step."**

### Slide 15: Evaluating a quadratic expression
*[Diagram: C++ statement with steps]*
- **Statement:** `y = a * x * x + b * x + c;`
- **Step numbers under each operator:**
  - Step 1: first `*` (a × x)
  - Step 2: second `*` ((a × x) × x)
  - Step 3: `*` (b × x)
  - Step 4: first `+` (add step 2 and step 3)
  - Step 5: second `+` (add c)
  - Step 6: `=` (assign to y)

**[Handwritten]**
- Red arrow from `y` to the algebra **"y = ax² + bx + c"**. The statement is the C++ version of the quadratic formula.

*[Added]:* in C++, `x * x` is written instead of `x²`. There is no power operator in the arithmetic set shown here.

---

## 7. Assignment and Compound Operators

### Slide 16: Compound assignment operators (table)
*Printed:*

| Compound form | Longer equivalent | Meaning |
|---|---|---|
| `x += y` | `x = x + y` | add and store |
| `x -= y` | `x = x - y` | subtract and store |
| `x *= y` | `x = x * y` | multiply and store |
| `x /= y` | `x = x / y` | divide and store |
| `x %= y` | `x = x % y` | store the integer remainder |

*Handwritten:* none.

### Slide 17: Example
*Printed code:*
```cpp
int score = 10;
score = score + 5;   // score becomes 15
score += 3;          // score becomes 18
score *= 2;          // score becomes 36
```

*Trace of the values:*

| Statement | Value of score |
|---|---|
| `int score = 10;` | 10 |
| `score = score + 5;` | 15 |
| `score += 3;` | 18 |
| `score *= 2;` | 36 |

*Handwritten:* none.

---

## 8. Increment and Decrement

### Slide 18: Post-fix and pre-fix
*Printed:*
- To add 1 to a variable `x` and store the answer back in `x`, the long form is `x = x + 1`.
- The compact forms are `x++` (post-fix) or `++x` (pre-fix).
- So `x = x + 1` is the same as `x++` or `++x`.

*Handwritten:* none.

### Slide 19: Increment and decrement operators
*Printed code:*
```cpp
int completed = 4;
completed++;   // completed becomes 5
++completed;   // completed becomes 6
completed--;   // completed becomes 5
```

*Printed note:*
- When `++` or `--` is used as a statement by itself (standalone), the prefix and postfix forms have the same final effect.

*Trace of the values:*

| Statement | Value of completed |
|---|---|
| `int completed = 4;` | 4 |
| `completed++;` | 5 |
| `++completed;` | 6 |
| `completed--;` | 5 |

*Handwritten:* none.

### Slide 20: Prefix vs postfix inside an expression
*Printed code:*
```cpp
int value = 5;
int first = ++value;    // value becomes 6, then first receives 6

value = 5;
int second = value++;   // second receives 5, then value becomes 6
```

*Printed note:*
- The difference matters when the operator is used inside a larger expression. The prefix form changes the variable **before** its value is used or assigned. The postfix form uses or assigns the **old** value, and then changes the variable.

*Results:*
- `first` = 6, and `value` = 6 after the first pair of statements.
- `second` = 5, and `value` = 6 after the second pair of statements.

*Handwritten:* none.

### Slide 21: Good practice
*Printed:*
- Avoid writing several updates to the same variable in one complicated expression.
- Separate statements are easier to read, trace, test, and maintain.

*Handwritten:* none.

---

## 9. Input Example and Exercises

### Slide 22: Addition of two integer values (using cin)
*[Diagram: printed code with handwriting]*

*Printed code (lines 2 to 22):*
```cpp
// Addition program that displays the sum of two integers.
#include <iostream> // allows program to perform input and output

// function main begins program execution
int main()
{
    // variable declarations
    int number1; // first integer to add
    int number2; // second integer to add
    int sum;     // sum of number1 and number2

    std::cout << "Enter first integer: "; // prompt user for data
    std::cin >> number1;                  // read first integer from user into number1

    std::cout << "Enter second integer: "; // prompt user for data
    std::cin >> number2;                   // read second integer from user into number2

    sum = number1 + number2;               // add the numbers; store result in sum

    std::cout << "Sum is " << sum << std::endl; // display sum; end line
} // end function main
```

**[Handwritten]**
- Top right: **"3 + 4 = 7"** with an arrow pointing down to the `sum` line. Worked example: if the user enters 3 and 4, `sum` is 7.
- Bottom: **"Sum is 7"** with an arrow from `sum` in the output line. This shows the output for the input 3 and 4.

*Example run:*
```
Enter first integer: 3
Enter second integer: 4
Sum is 7
```

*Points to note:*
- `number1` and `number2` are read from the user with `cin`.
- `sum` stores the result of `number1 + number2`.
- `std::endl` ends the line after the output.

*[Note]:* the printed code uses `std::` on each line, while the earlier slides use `using namespace std;`. Both forms are correct.

### Slide 23: Example exercise (marks)
*Printed:*
> Write a C++ program that takes marks obtained by a student in three subjects and displays the total marks and average marks.

*Handwritten:* none.

*[Added]:* the answer uses three `int` (or `double`) variables for the marks, a `sum` variable, and `sum / 3` for the average. If the marks are integers and the average is stored as an `int`, the decimal part is lost. Use `double` for the average to keep it.

### Slide 24: Example exercise (rectangle)
*Printed:*
> Write a C++ program that takes the length and width of a rectangle and calculates and displays its area and perimeter.

*Handwritten:* none.

*[Added]:* area = length × width. Perimeter = 2 × (length + width). The formula for perimeter needs parentheses, so that the addition happens first (precedence rules from Slide 12).

### Slide 25: Example exercise (temperature)
*Printed:*
> Write a C++ program that takes temperature in Celsius and converts it into Fahrenheit using the formula: `F = (C × 9/5) + 32`.

*Handwritten:* none.

*[Added]:* if `C` is an `int`, the expression `C * 9 / 5` uses integer division, which drops the decimal part. For example, 25 °C gives `25 * 9 / 5 = 45`, but the correct answer is 77 °F. The result is correct only if the operands are `double`: write `9.0 / 5` or store `C` as a `double`. This is a common student error.

---

## 10. Summary

1. **Output:** `cout << ...` prints text and values. `\n` and `endl` start a new line.
2. **Input:** `cin >> variable` reads a value typed by the user. Prompts with `cout` tell the user what to enter.
3. **Arithmetic operators:** `+`, `-`, `*`, `/`, and `%`. The modulus `%` works only with integers and gives the remainder.
4. **Precedence:** parentheses first, then `*`, `/`, and `%`, then `+` and `-`. Operators at the same level run left to right.
5. **Compound operators:** `x += y` means `x = x + y`. The same pattern applies to `-=`, `*=`, `/=`, and `%=`.
6. **Increment and decrement:** `x++` and `++x` add 1, and `x--` and `--x` subtract 1. The difference between the prefix and postfix forms matters only inside a larger expression.
7. **Good practice:** avoid complicated expressions that update the same variable several times. Use separate statements.

---

## Notes on Uncertain Items and Errors in the Slides
- Slide 2: the printed output shows `to` without the leading space that the code prints.
- Slide 4: `completeedLabs` is declared with a typo, and `completedLabs` is used later. This is a compile error.
- Slide 9: the rule at the bottom is handwritten, and the last words are partly hard to read.
- Slide 13: the crossed-out line is missing parentheses around the sum.
- Slide 22: the printed code uses `std::` on each line, which differs from the earlier style.
