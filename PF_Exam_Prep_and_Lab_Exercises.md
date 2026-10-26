# PF Exam Preparation: Lab Exercises, Common Errors, and Past Questions

**Course:** Programming Fundamentals (PF)
**Sources:** Preparation notes (untitled.txt), lab report screenshots (Images 1 to 3 and 6), and mid-term exam papers Fall 2025 (Images 4 and 5)

**Legend**
- *Source:* the wording comes from the original material
- **[Added]:** a teaching point added by these notes
- **[Note]:** a remark about the material itself

---

## Table of Contents

1. How to prepare for the paper
2. Errors to look for in code (checklist)
3. Writing clear conditions (reference table)
4. Lab exercises
5. Logic and common mistakes
6. Past exam questions (Fall 2025 mid-term)
7. Quick revision points

---

## 1. How to Prepare for the Paper

*Source (translated from the preparation notes):*

- Go through the examples in all the lab reports. Scenario-type questions are also important.
- If a problem is given in the paper and you are asked to write a program for it:
  1. First, understand the problem.
  2. Then think about the logic.
  3. Only then start writing the code.
- Last year's course taught **C**, but this year's course uses **C++**. Learn the C++ syntax, even when a past paper is written in C.
- The last year's paper contains an **array** question. Arrays were not covered yet, so you may ignore it.
- Each lab report has a **COMMON MISTAKES** section that lists typical errors. Revise it.

---

## 2. Errors to Look for in Code

The paper may ask you to find errors in code. Remember that there are two kinds:
- **Syntax errors:** the code will not compile.
- **Logical errors:** the code compiles, but the output is wrong.

Check the following points:

1. **Missing semicolon `;`** at the end of a statement.
2. **Correct stream operators:** `<<` for `cout`, and `>>` for `cin`.
3. **Declaring a `char` variable** uses single quotes, for example `char opr = '+';`.
4. **Double quotes** must start and end a string. For example, `cout << "Hi;` is missing its closing quote.
5. **Curly braces in if-else:** use `{ }` when the `if` or `else` body has more than one statement.
6. **Single `=` in a condition** is an assignment, not a comparison. `if (a = 2)` is wrong. Use `if (a == 2)`.
7. **`else if`** must be written with a space. `elseif (condition)` is wrong.
8. **`break;`** must be used at the end of each `case` in a `switch`.
9. **Colon `:`** comes after each `case` label, for example `case 1:`.

---

## 3. Writing Clear Conditions

*Source: Lab report, section 4.2 "Writing clear conditions"*

| Need | Condition | Meaning |
|---|---|---|
| At least 50 marks | `marks >= 50` | 50 is included. |
| Below 18 years | `age < 18` | 18 is not included. |
| Exactly choice A | `choice == 'A'` | Use `==` for comparison. |
| Not equal to zero | `value != 0` | True for every non-zero value. |
| Inside 1 to 10 | `value >= 1 && value <= 10` | Both limits must be satisfied. |
| Outside 1 to 10 | `value < 1 \|\| value > 10` | Either outside case is enough. |

*Source note (translated):* the table shows how to write conditions for MCQ questions. Try to write the full code from the table, and understand each row.

---

## 4. Lab Exercises

### Exercise 3: Test number properties

*Source:*
> Read an integer. Use separate clear decisions to report whether it is positive, negative, or zero, and whether it is even or odd. Remember that zero is even. Record your conditions before coding.

**[Added]:** write down your conditions in plain English before you write any C++ code.

*Reference example from the preparation notes:*

```cpp
int num;

cout << " Type a number ";
cin >> num;

if (num > 0)
{
    cout << "Number is positive" << endl;
}
else if (num < 0)
{
    cout << "Number is negative" << endl;
}
else
{
    cout << " Number is zero" << endl;
}

if (num % 2 == 0)
{
    cout << "Number is Even";
}
else
{
    cout << "Number is Odd";
}
```

**[Added]:** `0` is printed as "Number is zero" in the first block, and "Number is Even" in the second block. This is correct, because zero is even.

### Exercise 4: Correct a range ladder

*Source code:*

```cpp
if (marks >= 50) grade = 'D';
else if (marks >= 60) grade = 'C';
else if (marks >= 70) grade = 'B';
else if (marks >= 80) grade = 'A';
else grade = 'F';
```

*Source task:*
> Explain why `marks = 85` receives the wrong grade. Reorder the conditions, add a validity check for 0 to 100, and test 49, 50, 79, 80, 100, and 101.

**Explanation of the error:** the first condition, `marks >= 50`, is true for 85. The `if` chain stops at the first true condition, so 85 gets `'D'`. The `'A'` branch is never reached.

**[Added]:** to fix this, check the highest range first, and add a validity check:

```cpp
if (marks < 0 || marks > 100)
{
    cout << "Invalid marks";
}
else if (marks >= 80) grade = 'A';
else if (marks >= 70) grade = 'B';
else if (marks >= 60) grade = 'C';
else if (marks >= 50) grade = 'D';
else grade = 'F';
```

Test values: 49 (F), 50 (D), 79 (C), 80 (A), 100 (A), 101 (invalid).

*Check:* 79 gives 'C', because 79 is not 80 or above, but is 60 or above and below 70. Re-check this carefully when you test the code.

### Example 2: Finding the larger value or equality

*Source code:*

```cpp
if (first > second)
{
    cout << "First is larger" << endl;
}
else if (second > first)
{
    cout << "Second is larger" << endl;
}
else
{
    cout << "The values are equal" << endl;
}
```

**[Added]:** this is a good model for comparing two values. Each `if` checks one case, and the `else` covers the last case, where the values are equal.

### Scenario: Passenger age category

*Source (translated):*
> Read a passenger's age. Reject negative ages. Otherwise assign:
> - **Infant** for 0 to 2
> - **Child** for 3 to 12
> - **Student** for 13 to 25
> - **Adult** for 26 to 59
> - **Senior** for 60 or above
>
> Test every boundary and record the chosen category.

**Boundary test values:** −1, 0, 2, 3, 12, 13, 25, 26, 59, 60.

**[Added]:** write the conditions from the highest range down, or use boundaries carefully. For example:

- Age < 0: "Invalid age"
- Age ≤ 2: Infant
- Age ≤ 12: Child
- Age ≤ 25: Student
- Age ≤ 59: Adult
- Otherwise: Senior

Record the expected category for each test value before you run the code.

---

## 5. Logic and Common Mistakes

### Range checks must start from the highest value

*Source (translated):*
> This program contains a logical error. The output will be wrong for the highest marks. When checking a range of values with `if-else-if`, start from the highest range and go down to the lowest. The first condition should be `if (marks >= 80)`, and the last one should be `if (marks >= 50)`.

*See Exercise 4 above for the corrected version.*

### Integer division

*Source (translated):*
> If the numerator and the denominator are both declared as `int`, the division gives an `int` result with no decimal part.

**Example from the notes:**

```cpp
int a = 2, b = 5;
cout << a / b;    // Output: 0
```

*[Note]:* the preparation notes give the answer as 2 for an MCQ. That is not correct for `a / b` with `a = 2` and `b = 5`. Integer division gives `2 / 5 = 0`, because the decimal part is lost. The output is `0`. Check this carefully, because a similar question may appear on the paper.

**[Added]:** to get a decimal result, make at least one operand a `double`, for example `(double) a / b` or `2.0 / 5`.

---

## 6. Past Exam Questions: Mid-Term, Fall 2025

*Course:* Programming Fundamentals. *Instructors:* Mr. Imran Rasheed and Mr. Muhammad Usman.
*Rule on the paper:* each line of code must be commented.

**[Note]:** the papers are written in C (`printf`, `#include <stdio.h>`). This year's course uses C++, so write answers using `cout` and `cin`, following the C++ syntax you have learned.

### Paper 01, Question 1 [15 marks]

*Source:* "What will be the output of the following C programs? Identify the error if any."

**Program 01**

```c
#include <stdio.h>
int main() {
    int i, j;
    for (i = 1; i <= 3; i++) {
        printf("outer: ""%d ", i);
        for (j = 1; j <= 5; j++) {
            printf("inner: ""%d ", j);
        }
        printf("\n");
    }
    return 0;
}
```

**Program 02**

```c
#include <stdio.h>
int main()
{
    int i;
    for (i = 1; i <= 5; i++) {
        if (i == 3) {
            break; }
        printf("%d\n", i); }
    return 0;
}
```

**[Added] points to check:**
- In Program 01, the string `"outer: ""%d "` has a doubled quote. Check how a string is opened and closed.
- In Program 02, consider what `break` does inside the `for` loop, and which values are printed.

### Paper 03, Question 3 [10 marks]

*Source:* "Write a C program that reads 10 integers from the user into an array, increments each element by 2, and then calculates the sum of all the elements in the array."

**[Note]:** this question uses an array. Arrays were not covered yet, so you may ignore it, as the instructor said.

### Paper 03, Question 4 [10 marks]

*Source:*

A customer in a store is purchasing five items. The prices of the five items are:
- Price of item 1 = $12.95
- Price of item 2 = $24.95
- Price of item 3 = $6.95
- Price of item 4 = $14.95
- Price of item 5 = $3.95

*Task:* write a program that holds the prices of the five items in five variables. Display each item's price, the subtotal of the sale, the amount of sales tax, and the total. Assume the sales tax is 6%.

**[Added]:** use `double` variables for the prices, because they contain decimal values. Subtotal = sum of the five prices. Tax = subtotal × 0.06. Total = subtotal + tax.

### Paper 03, Question 5 [5 marks]

*Source:* "Find the error if any and rewrite the code."

```c
#include <stdio.h>
int main() {
    int i = 1;
    int j;
    while (i <= 3) {
        j = 1;
        while (j <= 5) {
            printf("%c ", j);
            j++;
        }
        printf("\n this is outer loop ");
        i++;
    }
    return 0;
}
```

**[Added] points to check:**
- The format `%c` prints a character. Consider whether `%d` is the right format for an integer `j`.
- The `printf` for "this is outer loop" runs once for each pass of the outer loop. Check whether its position is correct.
- Check that every string is properly closed.

---

## 7. Quick Revision Points

1. **Understand the problem, then plan the logic, then code.**
2. **Syntax errors** stop the program from compiling. **Logical errors** give the wrong output.
3. **Condition operators:** `==` compares, `=` assigns. `&&` needs both sides true, `||` needs one side true.
4. **Range ladders:** check from the highest range to the lowest, and add a validity check.
5. **`else if`** needs a space between `else` and `if`.
6. **`switch`:** each `case` ends with `break;` and a colon after the case label.
7. **Integer division** drops the decimal part. `2 / 5` is `0` when both values are `int`.
8. **Zero is even**, and zero is neither positive nor negative.
9. **Test boundaries:** test the lowest and highest values of each range, and the value just outside each range.
10. **Comment every line** of code, as the exam rules require.

---

## 8. Related Labs and Assignment

The topics in this guide are also covered in the labs and in Assignment No 1. See **PF_Labs_and_Assignment_Coverage.md** for the topic list of each lab and of the assignment. Two points matter for the labs:
- Lab 5 and Lab 6 practise the range-ladder and boundary checks from Section 4.
- Lab 6 Task 2 requires a `switch` statement, and that task must not use `if-else`.
