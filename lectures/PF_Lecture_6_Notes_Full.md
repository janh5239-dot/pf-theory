# PF Lecture 6: Decision Making (if, if…else, Logical Operators, switch)

**Source:** Mod_PF_Lec_6_Sp_2026 (PDF, 55 pages)
**Instructor:** Engr. Dr. Alauddin
**Topic:** Programming fundamentals

**Legend**
- *Printed:* text, code, or table from the original slide
- **[Handwritten]:** ink added by the lecturer
- **[Diagram]:** drawn figure, table, or annotated image
- **[Uncertain]:** handwriting that is hard to read; the most likely meaning is given
- **[Note]:** a possible error or inconsistency in the slide
- **[Added]:** a teaching point added by these notes, not on the slide

---

## Table of Contents

1. Title and transfer of control (Slides 1 to 2)
2. The if statement (Slides 3 to 7)
3. Relational and equality operators (Slides 8 to 12)
4. Writing programs with if (Slides 13 to 16)
5. Logical operators (Slides 17 to 23)
6. Common errors with if (Slides 24 to 25)
7. Operator precedence (Slides 26 to 28)
8. if…else (Slides 29 to 34)
9. Forms of if and if…else (Slides 35 to 38)
10. Nested if…else (Slides 39 to 42)
11. Blocks (Slides 43 to 45)
12. switch statement (Slides 46 to 54)
13. if-else vs switch (Slide 55)
14. Summary

---

## 1. Title and Transfer of Control

### Slide 1: Title
- *Decision Making*, Lecture 6 (Programming fundamentals), by Engr. Dr. Alauddin.

### Slide 2: Transfer of control
*Printed:*
- Normally, statements execute one after the other, in the order they are written. This is called **sequential execution**.
- C++ statements and keywords such as `if` and `else` let you specify that the next statement to execute may be other than the next one in sequence. This is called **transfer of control**.

*Handwritten:* none.

---

## 2. The if Statement

### Slide 3: The if statement
*[Diagram: two code examples with labels]*
- `if (x > 100) statement;`, with a **single-statement if body** under it.
- `if (speed <= 55) { statement; statement; statement; }`, with a **multiple-statement if body** under it. The note says **"no semicolon here"** after the closing brace.
- The slide text: the `if` statement lets a program take alternative action depending on whether a condition or expression is true or false.

**[Handwritten]**
- Red arrow at the title, labelled **"keyword."** The word `if` is a keyword.

### Slide 4: The general form of the if statement
*Printed:*
- Common general form:
  ```cpp
  if ( condition )
      statement;
  ```
- The more accurate general form:
  ```cpp
  if ( expression )
      statement;
  ```

*[Added]:* an expression is more general than a condition. The condition is just a special case of an expression that gives a true or false value.

### Slide 5: Zero and non-zero
*Printed:*
- In C++, a **non-zero** value is considered true, and **0** is considered false.

*Handwritten:* none.

### Slide 6: Valid if statements (with the value of each test)
*Printed:*
```cpp
if ( 3 + 2 % 5 )
    cout << "This works";
if ( a = 10 )
    cout "Even this works";
if ( -5 )
    cout "Surprisingly even this works";
```
- The slide says all three are valid `if` statements.
- `3 + 2 % 5` evaluates to `3 + 2 = 5`, which is non-zero, so it is true.
- `a = 10` assigns 10 to `a`, and the value of the assignment, 10, is non-zero, so it is true.
- `-5` is non-zero, so it is true.

*[Note]:* the second and third lines are missing the `<<` operator (`cout "..."` should be `cout << "..."`). The corrected version is shown on Slide 7.

*[Added]:* `if (a = 10)` is valid but usually a bug. It assigns rather than compares, so the `=` vs `==` error on Slide 24 comes from the same cause.

### Slide 7: A complete program with several if statements
*Printed code:*
```cpp
int main ()
{
    int a;

    if ( 3 + 2 % 5 )
        cout << "This works\n";
    if ( a = 10 )
        cout << "Even this works\n";
    if ( -5 )
        cout << "Surprisingly even this works\n";
    if ( 0 )
        cout << "Surprisingly even this works";
    cout << "\naaaaaaaaaaaaaaaaa";
}
```

*Output (from the code):*
```
This works
Even this works
Surprisingly even this works
aaaaaaaaaaaaaaaaa
```
- The `if ( 0 )` line never prints, because 0 is false.

*[Note]:* the slide does not include a `return` statement, which is acceptable as shown on earlier slides. The output line for `if (0)` is skipped entirely.

*Handwritten:* none.

---

## 3. Relational and Equality Operators

### Slide 8: Relational and equality operators
*Printed:*
- Conditions in `if` statements are formed with the equality and relational operators.

*Handwritten:* none.

### Slide 9: Table of operators
*[Diagram: table]*

| Standard algebraic operator | C++ operator | Sample C++ condition | Meaning of C++ condition |
|---|---|---|---|
| **Relational** | | | |
| `>` | `>` | `x > y` | x is greater than y |
| `<` | `<` | `x < y` | x is less than y |
| `≥` | `>=` | `x >= y` | x is greater than or equal to y |
| `≤` | `<=` | `x <= y` | x is less than or equal to y |
| **Equality** | | | |
| `=` | `==` | `x == y` | x is equal to y |
| `≠` | `!=` | `x != y` | x is not equal to y |

*[Added]:* the algebra symbol `=` is written as `==` in C++. The single `=` means assignment in C++.

*Handwritten:* none.

### Slide 10: Precedence of relational and equality operators
*Printed:*
- The relational operators (`<`, `<=`, `>`, `>=`) all have the same precedence and associate left to right.
- The equality operators (`==`, `!=`) have the same precedence, which is lower than that of the relational operators. They also associate left to right.

*Handwritten:* none.

### Slide 11: Reading the operators aloud
*Printed:*
- The equality operator `==` is read as "is equal to" or "double equals."
- The assignment operator `=` is read as "gets," "gets the value of," or "is assigned the value of."
- Example: `int d = 6;` means "d gets the value of 6," or "d is assigned the value of 6."

*Handwritten:* none.

### Slide 12: Example (x = 200)
*[Diagram: code with handwriting]*

```cpp
#include <iostream>
using namespace std;

int main()
{
    int x;

    cout << "Enter a number: ";
    cin >> x;
    if ( x > 100 )
        cout << "That number is greater than 100\n";
    return 0;
}
```

**[Handwritten]**
- A box labelled **x** containing **200**, with an arrow to the variable `x` in the code. The value entered is 200.
- Beside the `if` line: **"(200 > 100)"**, with a check mark. The condition is true, so the message prints.

*Output for the input 200:* `Enter a number: That number is greater than 100`

---

## 4. Writing Programs with if

### Slide 13: Using the if statement
*Printed:*
- Write a program that uses `if` statements to compare two numbers input by the user. If `x > y`, it should print "x is greater than y."

*Handwritten:* none.

### Slide 14: Solution (handwritten)
*[Handwritten code]*
```cpp
int main()
{
    int x, y;
    cin >> x >> y;
    if ( x > y )
        cout << "x is greater than y";
}
```
- Drawn beside the code: two boxes labelled **x** (with **10**) and **y** (with **20**). This is a test case, in which x is smaller than y, so the message does not print.
- The `if` line uses a bracket for the test. The code is not complete as drawn: the closing brace is partly shown.

*[Added]:* with x = 10 and y = 20, the message is not printed. A second `if` could test for the other case, or an `if…else` could cover both cases (see Slide 30).

### Slide 15: Checking code for errors (handwritten)
*[Handwritten, three numbered items]*

**(a)** `int = a;` is crossed out with an X. The declaration is missing the variable name before the `=`. Circled `=` inside the line shows the error. The corrected form is `int a;` or `int a = ...;`.

**(b)** `cout << a, b` is crossed out. The correct form is `cout << a << b;`, which has the check mark. A bracket beneath `cout << a << b` marks the correct version.

**(c)** `if (x > y) ... cout << ...` with `cin >> x >> y;` written under it. Partly readable, and the lines below it are not clear. [Uncertain]

*[Added]:* the three items test common mistakes. The first is a declaration error, and the second is a comma written where `<<` belongs.

### Slide 16: Reading input in different ways (handwritten)
*[Handwritten, three items]*

**(a)** Prompts separately for each value:
```cpp
cout << "Enter 1st value for x";
cin >> x;
cout << "Enter 2nd value for y";
cin >> y;
```
The variable `x` is highlighted in yellow.

**(b)** A single prompt with two values:
```cpp
cout << "Enter two values";
cin >> x >> y;
```
A check mark is drawn beside it, and a bracket groups it with (a).

**(c)** `cin >> x >> y;` alone, without a prompt. A check mark is drawn beside it.

*[Added]:* all three are valid. Option (a) asks for each value separately, and option (b) asks for both values together. Option (c) reads both values with no prompt, so the user gets no hint about what to type.

---

## 5. Logical Operators

### Slide 17: Logical operators
*Printed:*
- C++ provides logical operators to combine simple conditions into more complex ones.
- The logical operators are `&&` (logical AND), `||` (logical OR), and `!` (logical NOT, also called logical negation).

*Handwritten:* none.

### Slide 18: Logical AND (&&)
*Printed code:*
```cpp
if ( gender == 'F' && age >= 65 )
    cout << "seniorFemale";
```
- The condition is true only if **both** simple conditions are true.
- The simple condition on the left of `&&` is evaluated first. If necessary, the condition on the right is evaluated next.

*Handwritten:* none.

*[Added]:* because the left side is checked first, C++ does not evaluate the right side when the left side is already false. This is called short-circuit evaluation. It can matter when the right side has side effects.

### Slide 19: Writing a range check
*Printed:*
- The mathematical condition `3 < x < 7` is correct in algebra, but it does **not** work in C++ the way you might expect.
- Use `( x > 3 && x < 7 )` to get the correct result in C++.

*Handwritten:* none.

*[Added]:* in C++, `3 < x < 7` is read left to right. `3 < x` gives true or false (1 or 0), and then that result is compared with 7. The check always gives true, which is not what the range check intends.

### Slide 20: Logical OR (||)
*Printed:*
- Use the OR operator when either or both of two conditions must be true before choosing a path.
- Example:
  ```cpp
  if ( ( semesterAverage >= 90 ) || ( finalExam >= 90 ) )
      cout << "Student grade is A" << endl;
  ```

*Handwritten:* none.

### Slide 21: Truth table for ||
*[Diagram: table, with the caption "Fig. 5.16 | || (logical OR) operator truth table."]*

| expression1 | expression2 | expression1 \|\| expression2 |
|---|---|---|
| false | false | false |
| false | true | true |
| true | false | true |
| true | true | true |

*Handwritten:* none.

### Slide 22: Precedence of && and ||
*Printed:*
- The `&&` operator has higher precedence than `||`.
- Both operators associate from left to right.

*Handwritten:* none.

### Slide 23: Logical negation (!)
*Printed:*
- The `!` operator (logical NOT, or logical negation) reverses a condition's meaning.
- It is a **unary** operator, which means it takes only one operand.

*Handwritten:* none.

*[Added]:* `!` has higher precedence than the other logical and relational operators, so `!x > 5` is read as `(!x) > 5`. Use parentheses to make the intended meaning clear.

---

## 6. Common Errors with if

### Slide 24: The = and == error
*Printed code:*
```cpp
// Example to show a common error due to = and ==.
int main( )
{
    int i;
    cout << "Enter value of i ";
    cin >> i;
    if ( i = 5 )
        cout << "You entered 5";
    else
        cout << "You entered valueother than 5";
}
```

*Output of two runs:*
```
Enter value of i 200
You entered 5
Enter value of i 9999
You entered 5
```

*Explanation:* `i = 5` is an **assignment**, not a comparison. It sets `i` to 5 and gives the value 5, which is non-zero and therefore true. The program prints "You entered 5" for any input.

*Fix:* use `==` for comparison: `if ( i == 5 )`.

*Handwritten:* none.

### Slide 25: The stray semicolon
*Printed code:*
```cpp
// Example to show a common error in if programming
int main( )
{
    int i;
    cout << "Enter value of i ";
    cin >> i;
    if ( i == 5 ) ;
    cout "You entered 5";
}
```

*Printed note:*
- The semicolon after `if ( i == 5 )` makes the compiler read the statement as if it were written as:
  ```cpp
  if ( i == 5 )
      ;                       // empty statement
  cout << "You entered 5";
  ```
- The `cout` line therefore runs on every input, not only when `i` is 5.

*[Note]:* the line `cout "You entered 5";` is missing `<<`, so it will not compile as written. The explanation above assumes the `<<` is present.

*Handwritten:* none.

---

## 7. Operator Precedence

### Slide 26: Example (number1, number2)
*[Diagram: code with handwriting]*

```cpp
#include <iostream>  // allows program to perform input and output

// function main begins program execution
int main()
{
    int number1; // first integer to compare
    int number2; // second integer to compare

    cout << "Enter two integers to compare: "; // prompt user for data
    cin >> number1 >> number2;                 // read two integers from user

    if ( number1 == number2 )
        cout << number1 << " == " << number2 << endl;
    if ( number1 != number2 )
        cout << number1 << " != " << number2 << endl;
    if ( number1 < number2 )
        cout << number1 << " < " << number2 << endl;
}
```

**[Handwritten]**
- Boxes labelled **number1** (with **5**) and **number2** (with **5**). The two numbers are equal.
- Beside the output: **"5 == 5"**, which is the output for the first `if`.
- A downward arrow with check marks beside the `==` and `<` lines, and a **✗** beside the `!=` line. The check marks show the conditions that are true for this input. The cross shows that `!=` is false, so nothing is printed for it.
- A bracket with the note **"display value of variable number1"** [Uncertain: the last word is cut off at the slide edge].

*Output for input 5 and 5:*
```
5 == 5
```

*[Added]:* the program prints only one line because only one condition is true.

### Slide 27: Precedence table
*[Diagram: table]*

| Operators | Associativity | Type |
|---|---|---|
| `()` | [See caution in Fig. 2.10] | grouping parentheses |
| `*`, `/`, `%` | left to right | multiplicative |
| `+`, `-` | left to right | additive |
| `<<`, `>>` | left to right | stream insertion/extraction |
| `<`, `<=`, `>`, `>=` | left to right | relational |
| `==`, `!=` | left to right | equality |
| `=` | right to left | assignment |

*[Note]:* the table is titled "Precedence of the operators discussed so far," but it does not include the logical operators `&&`, `||`, and `!`, which were covered on Slides 17 to 23.

*[Added]:* the full order, from highest to lowest, is `!`, then the arithmetic operators, then the stream operators, then the relational operators, then the equality operators, then `&&`, then `||`, then assignment.

### Slide 28: Examples of conditions
*[Diagram: table]*

| Need | Condition | Meaning |
|---|---|---|
| At least 50 marks | `marks >= 50` | 50 is included. |
| Below 18 years | `age < 18` | 18 is not included. |
| Exactly choice A | `choice == 'A'` | Use `==` for comparison. |
| Not equal to zero | `value != 0` | True for every non-zero value. |
| Inside 1 to 10 | `value >= 1 && value <= 10` | Both limits must be satisfied. |
| Outside 1 to 10 | `value < 1 \|\| value > 10` | Either outside case is enough. |

*Handwritten:* none.

---

## 8. if…else

### Slide 29: The if…else double-selection statement
*Printed:*
- The `if…else` double-selection statement specifies one action when the condition is true, and a different action when it is false.

*Handwritten:* none.

### Slide 30: Pseudocode example
*Printed:*
```
If student's grade is greater than or equal to 60
    Print "Passed"
Else
    Print "Failed"
```
- The statement prints "Passed" if the grade is 60 or more, and "Failed" if it is less than 60.

*Handwritten:* none.

### Slide 31: The same logic in C++
*Printed:*
```cpp
if ( grade >= 60 )
    cout << "Passed";
else
    cout << "Failed";
```

*Handwritten:* none.

### Slide 32: Syntax for if…else
*[Diagram: two syntax examples]*
- **Single-statement form:**
  ```cpp
  if ( x > 100 )
      statement;
  else
      statement;
  ```
  Labels: **Single-statement if body** and **Single-statement else body**.
- **Multiple-statement form:**
  ```cpp
  if ( zebra != 0 )
  {
      statement;
      statement;
  }
  else
  {
      statement;
      statement;
  }
  ```
  Labels: **Multiple-statement if body** and **Multiple-statement else body**. The label "Test expression" is placed above `x > 100` and `zebra != 0`.

*Handwritten:* none.

### Slide 33: Example (if…else with x)
*[Diagram: code with handwriting]*

```cpp
int main()
{
    int x;

    cout << "\nEnter a number: ";
    cin >> x;
    if ( x > 100 )
        cout << "That number is greater than 100\n";
    else
        cout << "That number is not greater than 100\n";
    return 0;
}
```

**[Handwritten]**
- A curved arrow from the **T** (true) label to the `if (x > 100)` branch, and an arrow from the **F** (false) label to the `else` branch with a cross mark beside the `else` output. This shows the two paths.
- A check mark beside the `if` line. A cross mark beside the `else` output line.
- Bottom notes, written as an alternative:
  ```
  else if ( x <= 100 )
  else  ...  x == 100
  ```
  The lecturer appears to be pointing out that the `else` branch also includes `x == 100`, and that the boundary could be written as `x <= 100` in an explicit test. [Uncertain: the lower text is partly cut off at the slide edge.]

*[Added]:* with the code as written, the input 100 prints "That number is not greater than 100," which is correct. The handwritten alternative makes the boundary explicit.

### Slide 34: Output of the program
*Printed output:*
```
Here's output from two different invocations of the program:

Enter a number: 300
That number is greater than 100
Enter a number: 3
That number is not greater than 100
```

*Handwritten:* none.

---

## 9. Forms of if and if…else

### Slide 35: Forms (a) and (b)
*Printed:*
- The `if` statement can take any of the following forms:
  - **(a)** `if ( expression ) do this;`
  - **(b)** `if ( condition ) { do this; and this; }`

*Handwritten:* none.

### Slide 36: Forms (c) and (d)
*Printed:*
- **(c)** `if ( condition ) do this; else do this;`
- **(d)** `if ( condition ) { do this; and this; } else { do this; and this; }`

*Handwritten:* none.

### Slide 37: Form (e), nested else
*Printed:*
```
if ( condition )
    do this;
else
{
    if ( condition )
        do this;
    else
    {
        do this;
        and this;
    }
}
```

*Handwritten:* none.

### Slide 38: Form (f), nested if inside the if branch
*Printed:*
```
if ( condition )
{
    if ( condition )
        do this;
    else
    {
        do this;
        and this;
    }
}
else
    do this;
```

*Handwritten:* none.

---

## 10. Nested if…else

### Slide 39: Nested if…else statements
*Printed:*
- Nested `if…else` statements test for multiple cases by placing `if…else` statements inside other `if…else` statements.
- Example pseudocode: print A for grades of 90 or more, B for 80 to 89, C for 70 to 79, D for 60 to 69, and F for all other grades.

*Handwritten:* none.

### Slide 40: Pseudocode for the grade example
*Printed:*
```
If student's grade is greater than or equal to 90
    Print "A"
Else
    If student's grade is greater than or equal to 80
        Print "B"
    Else
        If student's grade is greater than or equal to 70
            Print "C"
        Else
            If student's grade is greater than or equal to 60
                Print "D"
            Else
                Print "F"
```

*Handwritten:* none.

### Slide 41: C++ code for the grade example
*Printed code:*
```cpp
if ( studentGrade >= 90 )     // 90 and above gets "A"
    cout << "A";
else
    if ( studentGrade >= 80 ) // 80-89 gets "B"
        cout << "B";
    else
        if ( studentGrade >= 70 ) // 70-79 gets "C"
            cout << "C";
        else
            if ( studentGrade >= 60 ) // 60-69 gets "D"
                cout << "D";
            else // less than 60 gets "F"
                cout << "F";
```

**[Handwritten]**
- An arrow from the text **"variable"** to `studentGrade`. This marks the variable that the conditions test.

*[Added]:* the nesting is deep and hard to read. The next slide shows the same logic in a flatter form.

### Slide 42: The 2nd form of if…else
*Printed code:*
```cpp
if ( studentGrade >= 90 )   // 90 and above gets "A"
    cout << "A";
else if ( studentGrade >= 80 ) // 80-89 gets "B"
    cout << "B";
else if ( studentGrade >= 70 ) // 70-79 gets "C"
    cout << "C";
else if ( studentGrade >= 60 ) // 60-69 gets "D"
    cout << "D";
else // less than 60 gets "F"
    cout << "F";
```

*[Added]:* this is the same logic as Slide 41, with `else if` used instead of the indented nesting. C++ treats `else if` as a single `if` placed in the `else` branch, so the two forms behave identically.

---

## 11. Blocks

### Slide 43: Blocks
*Printed:*
- An `if` statement expects only one statement in its body. The `else` part also expects only one body statement.
- To include several statements in the body of an `if` or `else`, enclose them in braces `{ }`.
- A set of statements inside a pair of braces is called a **compound statement** or a **block**.

*Handwritten:* none.

### Slide 44: Example of blocks (code)
*Printed code:*
```cpp
if ( studentGrade >= 60 )
    cout << "Passed.\n";
else
{
    cout << "Failed.\n";
    cout << "You must take this course again.\n";
}
```

*Handwritten:* none.

### Slide 45: Explanation of the block
*Printed:*
- If `studentGrade` is less than 60, the program executes both statements in the body of the `else` and prints:
  ```
  Failed.
  You must take this course again.
  ```
- Without the braces, only the first statement would be part of the `else`. The second statement would run every time, and the output would be:
  ```cpp
  cout << "You must take this course again.\n";
  ```

*[Added]:* the difference is the scope of the `else`. Without braces, only the statement directly after `else` is the else body. The braces group both statements under the `else`.

---

## 12. The switch Statement

### Slide 46: Introduction to switch
*Printed:*
- The `switch` statement chooses one option from several alternatives.
- It is useful when one expression must be compared with several limited, known values.
- The `switch` keyword starts the statement and holds the expression whose value is evaluated.
- The `case` keyword gives a particular value that can match the value of the switch expression.

*Handwritten:* none.

### Slide 47: Break and default
*Printed:*
- The `break` keyword ends a case and stops execution from continuing into the next case.
- The `default` keyword gives the statements to run when none of the cases matches.

*Handwritten:* none.

### Slide 48: Switch syntax (with handwriting)
*[Diagram: syntax, with handwriting]*

*Printed syntax:*
```cpp
switch (n)
{
    case 1:
        statement;
        statement;
        break;
    case 2:
        statement;
        statement;
        break;
    case 3:
        statement;
        statement;
        break;
    default:
        statement;
        statement;
}
```
Labels: **Integer or character variable** (for `n`), **Integer or character constant** (for each `case`), and "Note: no semicolon here" after `switch (n)` and after the closing brace.

**[Handwritten]**
- Arrow to the word **"keywords"** above the code.
- Arrow to `switch (` labelled **"expression."** The expression is evaluated.
- Arrow to `case 1:` labelled **"const."** Each case label must be a constant.
- A bracket around `statement; break;` under case 1, with a note that the statements run for that case.
- A red arrow from **"if true"** into the body of case 2.
- A red bracket beside `break;` in the case 2 body, labelled **"causes the control to come out of switch if case matches."**
- A red bracket beside `default:` with a note partly cut off at the edge of the slide.

*[Added]:* the handwritten note "if true" shows that the body of a case runs when the expression matches its value. Each case body ends with `break`, which jumps to the end of the switch.

### Slide 49: General syntax (with comments)
*Printed syntax:*
```cpp
switch (expression)  // switch - evaluates the given expression.
                     // expression - produces a value that is compared with the case values.
{
    case value1:     // case - specifies a possible value of the expression
        statements;
        break;       // break - terminates the switch statement and exits it.

    case value2:
        statements;
        break;

    case value3:
        statements;
        break;

    default:         // default - executes when none of the cases matches.
        statements;
}
```

*Handwritten:* none.

### Slide 50: Rules for switch
*Printed:*
- Each case label must be a constant value.
- Without `break`, execution continues into the next case. `default` handles values that match no listed case.
- A `break` statement is present at the end of each case section.
- If the value of the switch variable does not match any case constant, control passes to the end of the switch without doing anything.

*Handwritten:* none.

### Slide 51: Break and fall-through
*Printed:*
- The `break` keyword makes the entire switch statement exit. Control goes to the first statement after the switch.
- Without `break`, control passes down, or "falls through," to the statements of the next case. This is usually not what you want.

*Handwritten:* none.

### Slide 52: Complete switch program (menu)
*Printed code:*
```cpp
int main()
{
    int choice;

    cout << "Enter a number (1 or 2): ";
    cin >> choice;

    switch (choice)
    {
        case 1:
            cout << "You entered One";
            break;
        case 2:
            cout << "You entered Two";
            break;
        default:
            cout << "Invalid choice";
    }
}
```

*Output for input 1:* `You entered One`
*Output for input 2:* `You entered Two`
*Output for input 3:* `Invalid choice`

*Handwritten:* none.

### Slide 53: Calculator with switch
*Printed code:*
```cpp
#include <iostream>
using namespace std;

int main ()
{
    double a, b;
    char operation;

    cin >> a >> operation >> b;

    switch (operation) {
        case '+': cout << a + b << endl; break;
        case '-': cout << a - b << endl; break;
        case '*': cout << a * b << endl; break;
        case '/':
            if (b != 0) cout << a / b << endl;
            else cout << "Cannot divide by zero" << endl;
            break;
        default: cout << "Unknown operation" << endl;
    }
}
```

*Example:* input `8 / 2` prints `4`. Input `8 / 0` prints `Cannot divide by zero`. Input `8 % 2` prints `Unknown operation`, because `%` is not a case.

*[Added]:* the `case '/'` branch needs its own check for zero, because division by zero is not allowed. The `if` is placed inside the case, followed by its own `break`.

### Slide 54: Handwritten notes on case bodies
*[Handwritten]*
- Two alternative forms of the same case:
  1. **Option 1:**
     ```cpp
     case '+':
         c = a + b;
         cout << c;
         break;
     ```
     with a check mark beside it. The word "rest" [Uncertain] is crossed out above `c = a + b`.
  2. **OR, option 2:**
     ```cpp
     case '+':
         cout << a + b;
         break;
     ```
     with a check mark beside it.
- *Meaning:* both forms give the same result. Option 1 stores the sum in `c` first, and option 2 prints the expression directly.

*Printed:* none.

### Slide 55: if-else vs switch
*Printed table:*

| Use if or else-if when | Use switch when |
|---|---|
| Testing ranges, such as `marks >= 50` | Testing exact choices, such as 1, 2, or 3 |
| Combining conditions with `&&` or `\|\|` | One expression is compared with fixed constant values |
| Different branches need different expressions | The code represents a menu or category selection |

*[Added]:* `switch` cannot test ranges such as `marks >= 50`, because each `case` must be a constant. Use `if` or `else if` for ranges.

---

## 13. Summary

1. **Transfer of control:** `if`, `else`, and `switch` change the order in which statements run.
2. **Truth values:** 0 is false, and any non-zero value is true.
3. **Relational operators:** `<`, `<=`, `>`, `>=`. **Equality operators:** `==`, `!=`. Use `==` to compare and `=` to assign.
4. **Logical operators:** `&&` (both must be true), `||` (either can be true), `!` (reverses a condition). Write ranges as `x > 3 && x < 7`, not `3 < x < 7`.
5. **Precedence:** `!` first, then arithmetic, relational, equality, `&&`, then `||`.
6. **if…else:** chooses one of two paths. Use braces `{ }` to group several statements into one body.
7. **Nested and else-if chains:** test several ranges in order. The `else if` form is easier to read.
8. **switch:** chooses one case from a list of constant values. Each case ends with `break`, and `default` handles all other values.
9. **Common errors:** `=` used for `==`, a stray semicolon after `if (...)`, and a missing `break` in a switch.

---

## Notes on Uncertain Items and Errors in the Slides
- Slide 6: the second and third lines are missing `<<`.
- Slide 7: the last line of output is the string `aaaaaaaaaaaaaaaaa`, printed on its own line.
- Slide 14: the code is incomplete, and the closing brace is partly shown.
- Slide 15 (c): the code is partly readable, and the lines below it are not clear.
- Slide 25: the line `cout "You entered 5";` is missing `<<`.
- Slide 26: the final word in the note "display value of variable number1" is cut off at the edge of the slide.
- Slide 27: the table omits the logical operators `&&`, `||`, and `!`.
- Slide 33: the handwritten alternative at the bottom is partly cut off at the edge of the slide.
- Slide 48: the note beside `default:` is partly cut off at the edge of the slide.
- Slide 54: the word above `c = a + b` is hard to read.
