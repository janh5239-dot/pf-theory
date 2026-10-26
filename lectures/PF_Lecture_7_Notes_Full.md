# PF Lecture 7: Repetition Statements (Loops)

**Source:** Mod_PF_Lec_7_Sp_2026 (PDF, 20 pages)
**Instructor:** Engr. Dr. Alauddin
**Topic:** Programming fundamentals

**Legend**
- *Printed:* text, code, or syntax from the original slide
- **[Handwritten]:** ink added by the lecturer
- **[Diagram]:** drawn figure or annotated image
- **[Uncertain]:** handwriting that is hard to read; the most likely meaning is given
- **[Note]:** a possible error or inconsistency in the slide
- **[Added]:** a teaching point added by these notes, not on the slide

---

## Table of Contents

1. Title and introduction to loops (Slides 1 to 2)
2. The while loop: syntax (Slides 3 to 4)
3. The while loop: counting examples (Slides 5 to 8)
4. Indefinite while loops and common errors (Slides 9 to 12)
5. Input from the keyboard (Slide 13)
6. The do…while loop (Slides 14 to 20)
7. Summary

---

## 1. Title and Introduction

### Slide 1: Title
- *Repetition Statements (Loops)*, Lecture 7 (Programming fundamentals), by Engr. Dr. Alauddin.

### Slide 2: Loops
*Printed:*
- Loops are control instructions that execute a section of code a fixed number of times.
- The repetition continues while a condition is true. When the condition becomes false, the loop ends, and control passes to the statements after the loop.
- Three kinds of loops in C++:
  - the **while** loop,
  - the **do…while** loop, and
  - the **for** loop.

*[Note]:* the slide says "a fixed number of times," but the while loop is not limited to a fixed count. Slide 11 shows an indefinite loop. A better description is "repeat a section of code while a condition is true."

*Handwritten:* none.

---

## 2. The while Loop: Syntax

### Slide 3: General form of the while loop
*[Diagram: syntax, with handwriting]*

*Printed syntax:*
```cpp
initialization;                 // executed once
while ( loopContinuationCondition )
{
    statement
    increment;
}
```

**[Handwritten]**
- An arrow from the word **"initialization"** to the note **"executed once."** The initialization runs one time, before the loop starts.
- Arrow to the note **"variable that controls while loop."** The variable named in the initialization is the loop-control variable.
- A red arrow labelled **"Keyword"** pointing at `while`. The word `while` is a keyword.
- A small check mark below the box.

### Slide 4: The while loop: syntax (examples)
*[Diagram: syntax examples, with handwriting]*

*Printed:*
- **Single-statement loop body:**
  ```cpp
  while ( n != 0 )       // Note: no semicolon here
      statement;
  ```
- **Multiple-statement loop body:**
  ```cpp
  while ( v2 < 45 )      // Note: no semicolon here
  {
      statement;
      statement;
      statement;
  }                      // Note: no semicolon here
  ```
- The slide labels the test expression and the single-statement and multiple-statement loop bodies.

**[Handwritten]**
- In the single-statement form, the words **"increment;"** and a closing brace are written after the `statement;` line. This shows that a loop body should contain an update to the control variable, and that braces are used when there is more than one statement.
- In the multiple-statement form, the word **"increment"** is written near the third `statement;`, pointing at the place where the update should go.

*[Added]:* the loop continues only while the condition is true. Each pass must change the control variable so that the condition eventually becomes false. Otherwise the loop never ends (see Slide 11).

---

## 3. The while Loop: Counting Examples

### Slide 5: Example 1: display "welcome" 10 times
*Printed:* display "welcome" 10 times using a while loop.

*[Diagram: code with numbered steps, with handwriting]*

**Code (handwritten):**
```cpp
int main( )
{
    int i = 0;               // loop counter variable
    while ( i < 10 )
    {
        cout << "Welcome";
        cout << endl;
        i = i + 1;           // i++
    }
}
```

**[Handwritten]**
- **Step numbers** drawn on the code: **1** on `int i = 0;`, **2** on the `while` test, **4** on the first body line, **6** on `i = i + 1`, **3** and **5** on the body statements, and **7** at the closing brace. The arrows show the flow back to the test. [Uncertain: some step numbers are overlapping and are not clearly placed.]
- A box at the top right showing the values of `i` from 0 to 10. The values 0 to 9 are highlighted, and 10 is not.
- The note **"0 → 9 (total 10 times)"** beside the box.
- Notes below: **"1st … 10th time"** pointing to the first and last passes, and **"i = 0; i <= 9"** with an arrow to the alternative test.
- **"// same as // i < 10"** written at the bottom right.

*Explanation:* `i` starts at 0. The loop runs while `i < 10`, so the body runs for i = 0, 1, …, 9. That is 10 times. `i <= 9` gives the same result as `i < 10`.

*[Added]:* the variable `i` goes from 0 to 9, not 1 to 10, because the counter starts at 0. The loop body runs once for each value of `i`.

### Slide 6: Example 2: display values from 1 to 10
*Printed:* display values from 1 to 10 using a while loop.

*[Diagram: code, with handwriting]*

**Code (handwritten):**
```cpp
int main( )
{
    int i = 1;
    while ( i <= 10 )
    {
        cout << i << endl;
        i++;
    }
}
```

**[Handwritten]**
- A box showing the values of `i` as **1, 2, 3, … 10**. The value **1** is crossed out and then recopied. Beside the box, the final value **11** is written, with the note "i" above the box.
- Output notes on the right: **"//O/P"** and the output lines **1, 2, 3, … 10**, each on its own line.
- A curved arrow traces the flow from the body back to the test.
- The note **"2, 4, 6"** near the test and the step numbers on the body.

**Output:**
```
1
2
...
10
```

*[Added]:* after the loop ends, `i` holds 11. The loop stops as soon as the test `i <= 10` is false.

### Slide 7: Example 3: display from 10 to 1
*Printed:* display from 10 to 1.

*[Diagram: code, with handwriting]*

**Code (handwritten):**
```cpp
{
    i = 10;
    while ( i >= 1 )
    {
        cout << i << endl;
        i--;
    }
}
```

**[Handwritten]**
- A box showing the values of `i` as **10, 9, 8, …**. The number **1** is written above the box, and the number **0** is written at the top right, with the note **"o/p"** above the output list.
- The output list, from top to bottom: **10, 9, … 1**.
- Step numbers **1**, **2**, **3**, and **4**.
- A note at the bottom right: **"for displaying 20 → 5 (i = 20, i >= 5)."** This is an extra example. The loop counts down from 20 to 5 when `i` starts at 20 and the test is `i >= 5`. [Uncertain: the arrow direction and the final value are hard to read.]

**Output:**
```
10
9
...
1
```

*[Added]:* `i--` is a decrement. The counter goes down, so the test uses `>=`.

### Slide 8: The while loop, Example 2 (printed code)
*Printed code:*
```cpp
#include <iostream>
using namespace std;
int main()
{
    int counter = 1;                 // declare and initialize control variable
    while ( counter <= 10 )          // loop-continuation condition
    {
        cout << counter << " ";
        ++counter;                   // increment control variable by 1
    }                                // end while
    cout << endl;                    // output a newline
}                                    // end main
```

*Output:*
```
1 2 3 4 5 6 7 8 9 10
```

*Explanation:* the values are printed on one line, separated by spaces. The `endl` after the loop moves the output to a new line.

*Handwritten:* none.

### Slide 9: Designing a loop for even, odd, and multiple values (handwritten)
*[Handwritten notes]*

- **"To display even values (2 to 20):"** with **"from 2 to 20"** highlighted.
  - Start: `i = 2`.
  - Test: `i <= 20`.
  - Update: `i = i + 2`.
  - The word **"include"** is written above "from," with arrows showing that both ends are included.
- **"from (0 to 20)"**, with the word **"include"**:
  - Start: `i = 0`, with test `i <= 20` and update `i = i + 2`.
- **"for odd (from 1 to 19)":**
  - Start: `i = 1`, with test `i <= 19` and update `i = i + 2`.
- **"divisible by 3 (from 3 to 21)":**
  - Note: "indg." (probably "indicates") under the range **3 to 21**.
  - Start: `i = 3`, with test `i <= 21` and update `i = i + 3`.

*[Added]:* the pattern is the same in every case. Choose the starting value, the test that includes the last value, and the update step. For "divisible by 3", the step is 3 and the range is from 3 to 21.

---

## 4. Indefinite Loops and Common Errors

### Slide 10: The condition may use relational or logical operators
*Printed:*
- The condition being tested may use relational or logical operators, as in these examples:
  ```cpp
  while ( i <= 10 )
  while ( i >= 10 && j <= 15 )
  while ( j > 10 && ( b < 15 || c < 20 ) )
  ```

*Handwritten:* none.

### Slide 11: Indefinite while loop (no increment)
*[Diagram: two code examples, with handwriting]*

**Left code (printed, with handwritten marks):**
```cpp
main( )
{
    int i = 1;
    while ( i <= 10 )
        cout << i;       // the printf line is crossed out
}
```

**Right code (corrected):**
```cpp
main( )
{
    int i = 1;
    while ( i <= 10 )
    {
        cout << i;
        i = i + 1;
    }
}
```

**[Handwritten]**
- Numbers **1, 2, 3** beside the left code showing the order of the steps: initialize, test, body.
- A box containing **i = 1**, and the output note **"o/p ⇒ 1"**. The program prints 1 over and over.
- A large brace and the note: **"No incrementation so condition is always true and program runs for indefinite time."**
- An arrow to the added line **`i = i + 1;`** in the corrected version.

*Explanation:* the left program never changes `i`, so `i <= 10` is always true. The loop repeats forever and prints `1` each time. The right program adds `i = i + 1;`, so the loop stops after 10 passes.

*[Added]:* an infinite loop is often caused by a missing update. Check that the body changes the variable used in the test.

### Slide 12: Find the output (the stray semicolon)
*Printed:*
```cpp
int i = 0;
while (i <= 10);
{
    cout << i;
    i = i + 1;
}
```
*Printed question:* "Find output for following."
*Printed note:* "Indefinite loop due to the semicolon (;) after 'while' parenthesis."

**[Handwritten]**
- An arrow from the semicolon after `while (i <= 10)` to the note **"No statement is depend on while"** [Uncertain: the note probably reads "no statement depends on while"]. The `while` loop has an empty body.
- A curved arrow from the empty body `{ ; }` back to the test, with the note **"while (i <= 10) { ; }"**. This shows the loop as the compiler reads it.
- The yellow highlight **"run for ever"** beside the empty loop.
- The green highlight **"never be executed"** beside the braced block `{ cout << i; i++; }`.

**Output:** the program prints nothing and never ends. The empty loop body does not change `i`, so the test `i <= 10` stays true forever. The block after the semicolon is never executed.

*[Added]:* a semicolon directly after the `while (...)` line ends the loop with an empty statement. The block that follows is not part of the loop.

---

## 5. Input from the Keyboard

### Slide 13: Important
**[Handwritten]**
- A bullet: **"user input is from keyboard,"** with a bracket and an arrow to the note **"use cin."**
- A second bullet, left blank.

*[Added]:* `cin >> variable;` is the way to read user input from the keyboard in C++. This matches the examples in earlier lectures.

---

## 6. The do…while Loop

### Slide 14: The do…while repetition statement
*Printed:*
- The `do…while` statement is similar to the `while` statement.
- In the `while` statement, the loop-continuation test happens at the beginning of the loop, before the body runs.
- In `do…while`, the test happens after the body runs. The body therefore always runs at least once.

*Handwritten:* none.

### Slide 15: Braces in do…while
*Printed:*
- Braces are not required in `do…while` if the body has only one statement.
- Most programmers include the braces anyway, to avoid confusion between `while` and `do…while`.

*Handwritten:* none.

### Slide 16: Recommended form
*Printed:*
- Better to use braces. The form is:
  ```cpp
  do                    // keyword
  {
      statement
  } while ( condition );
  ```

*Handwritten:* none.

*[Added]:* the `do…while` loop ends with a semicolon after the `while (condition)` line. This is the reverse of the `while` loop, which has no semicolon at the end of its header.

### Slide 17: Example 1: display "Welcome" 10 times (do…while)
*Printed:* display "Welcome" 10 times.

*[Diagram: code, with handwriting]*

**Code (handwritten):**
```cpp
int main( )
{
    int i = 1;                       // step 1
    do
    {
        cout << "welcome" << endl;   // steps 2, 4, 6
        i++;
    } while ( i <= 10 );             // steps 3, 5, 7
}
```

**[Handwritten]**
- Step **1** on `int i = 1;`.
- Steps **2, 4, 6** on the body lines, and steps **3, 5, 7** on the test.
- A curved arrow from the end of the loop back to the `do` line.
- The note **"must"** with an arrow to the semicolon after `while (i <= 10)`, which is required.
- A crossed-out line **"× i++;"** placed after the loop. The increment belongs inside the body, not after the loop.

*[Added]:* the `i++` after the loop would not run inside the loop, so the counter would never change. This is the error that the crossed-out line shows.

### Slide 18: Output of a do…while loop (handwritten)
*[Handwritten code]*
```cpp
int i = 1;
do
{
    cout << i << endl;
}
while ( i <= 10 );
i++;                 // crossed out, with a note: "never execute"
```

**[Handwritten]**
- A red **"O/P = ?"** at the top, asking the student to find the output.
- A brace beside the body with the note **"infinite loop."**
- A note at the bottom: **"never execute"** beside the `i++;` line. It is placed after the loop, so it is never reached.
- A small arrow and a crossed-out `i++` in the body, showing that `i` is never changed inside the loop.

**Output:** the program prints `1` again and again without end. The variable `i` is never updated inside the loop, so the test `i <= 10` stays true. The `i++;` after the loop is never executed.

*[Added]:* this is the same kind of error as Slide 11. The fix is to put `i++;` inside the body.

### Slide 19: Example 2: display 1 to 10 using do…while
*Printed:* display 1 to 10 using `do…while`.

*Handwritten:* none.

### Slide 20: Example 2: do…while (code)
*Printed code:*
```cpp
int main()
{
    int counter = 1;                  // initialize counter
    do
    {
        cout << counter << " ";       // display counter
        ++counter;                    // increment counter
    } while ( counter <= 10 );        // end do...while
}
```

*Output:*
```
1 2 3 4 5 6 7 8 9 10
```

*Explanation:* the body runs first, and then the test `counter <= 10` decides whether to repeat. Because the body runs before the test, the output starts at 1, and the loop ends after 10 is printed.

*Handwritten:* none.

---

## 7. Summary

1. **Loops** repeat a block of code while a condition is true. The three loop types in C++ are `while`, `do…while`, and `for`.
2. **while loop:** the test comes first, so the body may run zero times. The form is `initialization; while (condition) { body; increment; }`.
3. **Counting:** use a control variable, initialize it before the loop, test it in the condition, and update it in the body.
4. **Common errors:** no update (infinite loop), and a semicolon directly after `while (...)` (empty loop body).
5. **do…while loop:** the body runs first, so it always runs at least once. The condition is followed by a semicolon.
6. **Keyboard input:** use `cin >>` to read values from the user.

---

## Notes on Uncertain Items and Errors in the Slides
- Slide 2: "a fixed number of times" does not describe every while loop, because some loops depend on a condition rather than a count.
- Slide 5: some step numbers overlap, and their order is hard to follow.
- Slide 7: the note "for displaying 20 → 5" is partly unclear, and its arrow and final value are hard to read.
- Slide 9: the word "indg." (probably "indicates") is abbreviated.
- Slide 12: the note beside the semicolon is partly unclear. It probably says "no statement depends on while."
- Slide 18: the code uses a `while` with a semicolon and a crossed-out `i++`. The output is an infinite loop as written.
