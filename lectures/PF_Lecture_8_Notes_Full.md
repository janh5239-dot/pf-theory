# PF Lecture 8: Repetition Statements (The for Loop)

**Source:** Mod_PF_Lec_8_Sp_2026 (PDF, 39 pages)
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

1. Title (Slide 1)
2. The for loop: introduction and header (Slides 2 to 5)
3. Counting examples with for (Slides 6 to 9)
4. Optional parts of the header (Slides 10 to 13)
5. The semicolon error and loops without an increment (Slides 14 to 16)
6. Arithmetic in the header and counting down (Slides 17 to 19)
7. Behaviour when the condition is false, and variants (Slides 20 to 22)
8. Loop examples: step values and sequences (Slides 23 to 26)
9. Summing and related examples (Slides 27 to 28)
10. The comma operator (Slides 29 to 31)
11. The continue statement (Slides 32 to 34)
12. More examples: sum, largest, multiplication table, digits (Slides 35 to 39)
13. Summary

---

## 1. Title

### Slide 1: Title
- *Repetition Statements (Loops)*, Lecture 8 (Programming fundamentals), by Engr. Dr. Alauddin.

---

## 2. The for Loop: Introduction and Header

### Slide 2: The for loop
*Printed:*
- The `for` loop handles variable- or counter-controlled repetition.
- All the repetition details appear in a single line of code, called the **header**.
- The `for` statement includes:
  - an initialization,
  - a loop-continuation condition, and
  - an incrementation.

*Handwritten:* none.

### Slide 3: General form of the for statement
*Printed:*
- The general form of the statement is shown on the slide.
- The **initialization** expression sets the loop's control variable.
- The **loop-continuation condition** decides whether the loop continues.
- The **increment** changes the control variable.

*Handwritten:* none.

### Slide 4: For statement header components
*[Diagram: annotated header, with handwriting]*

*Printed:*
```cpp
for ( int counter = 1; counter <= 10; counter++ )
```
- **for:** keyword.
- **Control variable name:** `counter`.
- **Initial value of control variable:** `1`.
- **Required semicolon separator** after the initial value.
- **Final value of control variable for which the condition is true:** `10`, which is part of the loop-continuation condition `counter <= 10`.
- **Required semicolon separator** after the condition.
- **Increment of control variable:** `counter++`.

**[Handwritten]**
- A bracket under `int counter` with the word **"declaration"** [Uncertain: partly cut off at the left edge].
- A bracket under `counter` in the initialization and under `int counter`, with the note **"(both are allowed)."** This means that the control variable may be declared in the header, or declared earlier and only assigned in the header.

*[Added]:* in C++, `for (int i = 1; ...)` declares `i` for the loop only. The variable cannot be used after the loop ends.

### Slide 5: The for loop syntax
*[Diagram: syntax, printed]*

*Printed syntax:*
```cpp
for (j = 0; j < 15; j++)     // Note: no semicolon here
    statement;               // single-statement loop body

for (j = 0; j < 15; j++)     // Note: no semicolon here
{
    statement;
    statement;
    statement;
}                            // Note: no semicolon here
```
- The labels show a **single-statement loop body** and a **multiple-statement loop body**, which is a block of code.

*Handwritten:* none.

---

## 3. Counting Examples with for

### Slide 6: Example 1: display "Welcome" 10 times
*Printed:* write a program that displays "Welcome" 10 times.

*[Handwritten code with step numbers and a value box]*

```cpp
int main( )
{
    int i;
    for ( i = 0; i < 10; i++ )
        cout << "welcome" << endl;
}
```

**[Handwritten]**
- A box at the top right showing the value of `i`, with the first value crossed out and replaced by **1**. [Uncertain: the first value appears to be 0, with the overwritten value hard to read.]
- Step numbers:
  - **1** on `i = 0`
  - **2, 5, 8** on the test `i < 10`
  - **3, 6, 9** on the `cout` line
  - **4, 7** on the increment `i++`
- Arrows from the `i++` back to the test, and from the test to the body.

*Explanation:* the initialization runs once, then the test runs before each pass. The body runs while `i < 10`, and the increment runs after each pass. This matches the order of the step numbers.

*[Added]:* the body prints `welcome` 10 times, because `i` takes the values 0 to 9.

### Slide 7: Choosing the test for 10 repetitions
*[Handwritten]*
- Heading: **"i < or <= , > ? >="** [Uncertain: the question mark is written to show that the choice of operator is being considered].
- Heading: **"display 10 time."**
- **(a)** `i = 0 ⇒ i < 10 or i <= 9`. The note **"9 is included but 10 is not"** is written beside it, which is correct, because `i < 10` and `i <= 9` both stop before 10.
- **(b)** `i = 1 ⇒ i < 11 or i <= 10`. The note **"10 is included but 11 is not"** is written beside it, which is correct.

*[Added]:* the two forms give the same results. Starting at 0 with `i < 10` or `i <= 9` makes 10 passes. Starting at 1 with `i <= 10` or `i < 11` also makes 10 passes. Choose the start value and the test together, so that the loop runs the number of times you want.

### Slide 8: Example 2: display integer values from 1 to 10
*[Handwritten code]*

```cpp
int main( )
{
    int i;
    for ( i = 1; i <= 10; i++ )
    {
        cout << i << endl;
    }
}
```

**[Handwritten]**
- Circled step numbers **1** (`int i;`) and **2** (`for`) at the top.
- Step numbers **3, 6** on the test and **5, 8** on the increment, and **4, 7** on the `cout` line.
- Output written at the bottom: **"O/P = 1, 2, … 10"**, with **10** circled.

**Output:**
```
1
2
...
10
```

### Slide 9: The same program with a counter, printed
*Printed code:*
```cpp
#include <iostream>
using namespace std;
int main()
{
    for ( int counter = 1; counter <= 10; ++counter )
        cout << counter << " ";

    cout << endl;   // output a newline
}  // end main
```

*Output:*
```
1 2 3 4 5 6 7 8 9 10
```

*[Note]:* the printed code uses `++counter` in the header, where the earlier code used `counter++`. The two forms give the same result when they are used alone in the header (see Slide 13).

*Handwritten:* none.

---

## 4. Optional Parts of the Header

### Slide 10: The header expressions are optional
*Printed:*
- The three expressions in the `for` header are **optional**. The two semicolons, however, are **required**.
- If the loop-continuation condition is omitted, C++ assumes that the condition is true, which creates an infinite loop.

*[Added]:* the header must always have two semicolons, even when some expressions are missing:
```cpp
for ( ; ; )   // valid, and the loop runs forever
```

*Handwritten:* none.

### Slide 11: The initialization may be omitted
*Printed:*
- The initialization expression may be omitted if the control variable is initialized earlier in the program.
- Example:
  ```cpp
  int i = 1;
  for ( ; i <= 10; i = i + 1 )    // this also works
  ```

**[Handwritten]**
- A red bracket under `int i = 1;`, with an arrow pointing up at the empty part of the header before the first semicolon. This shows the omitted initialization.

*Handwritten:* as above.

### Slide 12: The increment may be omitted
*Printed:*
- The increment expression may be omitted if the increment is calculated by statements in the body of the `for`, or if no increment is needed.

*[Handwritten code]*
```cpp
for ( i = 0; i <= 2; )     // No increment in the header
{
    cout << "abc";
    i++;                   // increment in the body
}
```

**[Handwritten]**
- A note at the top right: **"No increment"** with an arrow to the header.
- A check mark beside the body with **"→ OK"** written beside it, because the increment is in the body.
- A note at the right: **"if removed, still OK"** [Uncertain: the note is partly cut off at the edge of the slide].

*[Added]:* the loop still works without the header increment, but it is easy to forget the update. Keep the increment in the header unless there is a clear reason to move it.

### Slide 13: Equivalent statements
*Printed:*
- All of the statements below do the same thing:
  ```cpp
  counter = counter + 1;
  counter += 1;
  ++counter;
  counter++;
  ```

**[Handwritten]**
- A bracket grouping the four forms, with the note **"can't be used for ≥ +1"** [Uncertain: the note is written as a bracket from the four forms to the words that follow].
- Below it, an arrow with **"+2, +3, …"** and the note **"can be used only for +1."**
- An item crossed out: **"i++ + 7 ✗"**. The lecturer is pointing out that `++` and `--` can only change a variable by exactly 1. For other steps, use `+=` or `-=`, as in `counter += 2;`.

*[Added]:* use `i += 7` or `i = i + 7` to step by 7. `i++7` is not valid C++.

---

## 5. The Semicolon Error and Loops without an Increment

### Slide 14: A semicolon directly after the header
*Printed:*
- Placing a semicolon immediately to the right of the closing parenthesis of a `for` header makes the body of that `for` statement an **empty statement**.
- This is usually a **logic error**.

**[Handwritten]**
- Code written in red:
  ```cpp
  for ( i = 1; i <= 2; i++ ) ;     // the semicolon is circled
      cout << "abc";
  ```
- A red arrow from the circled semicolon to a note **"Not dependent on for."** The `cout` line runs once, not once per pass, because it is not part of the loop body.
- A second version written to the right of the first, with a `for(...)` header followed by `;`, and the note **"cout <<"** at the bottom. This shows that the `cout` is outside the loop.

*Explanation:* with the stray semicolon, the loop does nothing on each pass. The `cout` runs once after the loop. The output is `abc` printed once, not twice.

### Slide 15: Tracing the stray semicolon
*[Handwritten]*
- Step numbers **1** on the initialization, **2, 5** on the test, **3, 6** on the increment, and **4, 7** on the body. The semicolon is circled.
- A note written on the left: **"8"** with an arrow to the `cout` line, showing that the `cout` line is run as step 8, after the loop.
- The note **"Not dependent on for"** with an arrow to `cout <<`.
- Two correct forms at the bottom:
  1. `for ( ... )` with the body on the next line, and `cout` written under it, with a bracket around the body.
  2. `for ( ) { ... }` with braces around the body, shown with a curved arrow back to the `for` line.
- The braces make the body a block that repeats with each pass.

### Slide 16: No increment with the stray semicolon
*[Handwritten]*
```cpp
for ( i = 1; i <= 3; )     // no increment, and a semicolon at the end
;
{
    i++;
    cout << "abc";
}
```
- A bracket around the header with the note **"No increment"** and an arrow to **"infinite loop."**
- The block `{ i++; cout << "abc"; }` is marked with the note **"never executed."**

*Explanation:* the semicolon makes the body empty, and the header has no increment. The test `i <= 3` stays true because `i` never changes. The loop runs forever, and the block after the semicolon is never executed.

*[Added]:* this combines the two errors from Slides 12 and 14. Both must be fixed to make the loop work.

---

## 6. Arithmetic in the Header and Counting Down

### Slide 17: Arithmetic expressions in the header
*Printed:*
- The initialization, loop-continuation condition, and increment expressions may contain arithmetic expressions.

*Handwritten:* none.

### Slide 18: Example of an arithmetic header
*Printed:*
- If `x = 2` and `y = 10`, and `x` and `y` are not changed in the loop body, then the header
  ```cpp
  for ( int j = x; j <= 4 * x * y; j += y / x )
  ```
  is equivalent to
  ```cpp
  for ( int j = 2; j <= 80; j += 5 )
  ```

*Working out:* `4 * x * y = 4 * 2 * 10 = 80`, and `y / x = 10 / 2 = 5`. The two headers match.

*Handwritten:* none.

### Slide 19: Negative increments count downward
*Printed:*
- The increment of a `for` statement can be negative. In that case it is really a decrement, and the loop counts downward.

*Handwritten:* none.

### Slide 20: Counting down from 10 to 1
*[Handwritten]*

**Heading:** "To display 10 to 1 in reverse order."

```cpp
int i;
for ( i = 10; i >= 1; i-- )
    cout << i;
```

- Step numbers **1** on `int i;`, **2, 5, 8** on the test, and **3, 6** on the `cout`, **4, 7** on the decrement.
- A box showing the values of `i`, with the values **10, 9, 8** and the value **1** at the end. Some values are crossed out.
- Output written at the bottom: **"O/P ⇒ 10 9 … 1."**

*[Added]:* the output is printed without spaces, so the numbers run together: `10987654321`. Add `" "` or `endl` to separate them.

---

## 7. Behaviour When the Condition Is False, and Variants

### Slide 21: The loop body may never run
*Printed:*
- If the loop-continuation condition is false at the start, the body of the `for` statement is not performed.
- Execution goes straight to the statement after the `for`.

*Handwritten:* none.

### Slide 22: Declaration, multiple initializations, and for(;;)
*Printed:*
- A variable may be declared in the header:
  ```cpp
  for ( int j = numb; j > 0; j-- )
  ```
- Several initializations are allowed, separated by commas:
  ```cpp
  for ( j = 0, alpha = 100; j < 50; j++ )
  ```
- The expression `for (;;)` is the same as a `while` loop with a test expression of `true`.

*Handwritten:* none.

---

## 8. Loop Examples: Steps and Sequences

### Slide 23: Examples using for statements
*[Diagram: four examples, with handwriting]*

*Printed examples:*
- **a)** Vary the control variable from 1 to 100 in increments of 1:
  ```cpp
  for ( int i = 1; i <= 100; ++i )
  ```
- **b)** Vary the control variable from 100 down to 1 in decrements of 1:
  ```cpp
  for ( int i = 100; i >= 1; --i )
  ```
- **c)** Vary the control variable from 7 to 77 in steps of 7:
  ```cpp
  for ( int i = 7; i <= 77; i += 7 )
  ```
- **d)** Vary the control variable from 20 down to 2 in steps of −2:
  ```cpp
  for ( int i = 20; i >= 2; i -= 2 )
  ```

**[Handwritten]**
- A check mark beside **a)** and the note **"To display 1 → 100."**
- An arrow at **b)** with the note **"100 → 1."**
- A note beside **c)** reading **"multiples of 7."**
- A note beside **d)** with the step written as **"i = i − 2"**, and a line below showing **"2 − 1 = 2 + (−1)."** This explains that subtracting 2 is the same as adding −2.
- The sequence **"20, 18, 16, … 2"** written at the bottom.

*[Added]:* the four loops show the common forms: a step of +1, a step of −1, a step of +7, and a step of −2.

### Slide 24: Display from 7 to 70, only multiples of 7
*[Handwritten]*

**Heading:** "Display from 7 to 70, only multiples of 7 included."

```cpp
int main( )
{
    int i;
    for ( i = 7; i <= 70; i += 7 )
        cout << i;
}
```

- The note **"i = i + 7"** with an arrow to `i += 7`, which means the same thing.
- A note **"// i++ × "** written in the margin, with a cross mark, showing that `i++` is not used here because it steps by 1.

*[Note]:* the code is not complete as written, because the `cout` line is not inside braces. It still works, because the loop body is a single statement.

*Output (as the code runs):*
```
7142128354249566370
```
[Added: the numbers run together because no space or `endl` is printed. The values printed are 7, 14, 21, 28, 35, 42, 49, 56, 63, and 70. Note that 70 is included, because the test is `i <= 70`.]

### Slide 25: A sequence of values with step 3
*[Diagram: printed example, with handwriting]*

*Printed:* vary the control variable over the sequence 2, 5, 8, 11, 14, 17.

```cpp
for ( int i = 2; i <= 17; i += 3 )
```

**[Handwritten]**
- An arrow pointing to the control variable in the header, labelled **"change."** The step changes the control variable by 3 each time.
- Two short marks above the header, which are probably the step markers for the sequence.

*[Added]:* the loop stops at 17, because `i = 20` is not less than or equal to 17.

### Slide 26: A sequence of values with step −11
*[Diagram: printed example, with handwriting]*

*Printed:* vary the control variable over the sequence 99, 88, 77, 66, 55.

```cpp
for ( int i = 99; i >= 55; i -= 11 )
```

**[Handwritten]**
- A calculation: **"5 − 2 = 3 → subtract 2,"** and **"5 + (−2) = 3 → add −2."** This shows that subtracting and adding a negative number give the same result.
- A note **"decrement by 2"** and **"increment by −2"** at the bottom, pointing out that the step can be written either way.

*[Added]:* in this example the step is 11. The handwriting shows the principle with a smaller step of 2. The loop stops at 55, because the next value 44 is less than 55.

---

## 9. Summing Examples

### Slide 27: Example 3: sum the even integers from 2 to 20
*Printed:* write code using a `for` statement to sum the even integers from 2 to 20 (add 2, 4, 6, 8, … 20).

*Handwritten:* none.

### Slide 28: Example 4: sum all even values from 2 to 20
*Printed:* write code to sum all even values from 2 to 20.

*Handwritten:* none.

*[Added]:* one answer uses `for (int i = 2; i <= 20; i += 2) sum += i;`, with `int sum = 0;` before the loop. The result is 110.

---

## 10. The Comma Operator

### Slide 29: The comma operator
*Printed:*
- The initialization and increment expressions can contain comma-separated lists of expressions.
- The expressions are evaluated from left to right.
- The comma operator has the lowest precedence of all C++ operators.

*Handwritten:* none.

### Slide 30: The same text, repeated
*Printed:* the same text as Slide 29.

*Handwritten:* none.

*[Note]:* Slides 29 and 30 are identical in the source.

### Slide 31: Using the comma operator
*Printed:*
- The comma operator is often used in `for` statements. Its main use is to allow several initialization and increment expressions.
- For example, a `for` statement may have several control variables that must be initialized and incremented.

*[Added]:* an example is:
```cpp
for ( int i = 0, j = 10; i < j; i++, j-- )
    cout << i << " " << j << endl;
```
Here both `i` and `j` are initialized and updated in the same header.

*Handwritten:* none.

---

## 11. The continue Statement

### Slide 32: The continue statement
*Printed:*
- When `continue` runs inside a `while`, `for`, or `do…while` loop, it skips the remaining statements in the body and goes to the next iteration of the loop.
- It does **not** leave the loop, unlike `break`.

*Handwritten:* none.

### Slide 33: How continue affects each loop
*Printed:*
- In `while` and `do…while` loops, the loop-continuation test is evaluated right after the `continue` runs.
- In a `for` loop, the increment expression runs first, and then the loop-continuation test is evaluated.

*Handwritten:* none.

*[Added]:* the difference matters. In a `while` loop, a `continue` that skips the update causes the loop to repeat the same value. In a `for` loop, the update runs before the test, so the loop still progresses.

### Slide 34: Example of continue
*[Diagram: printed code, with handwriting]*

*Printed code:*
```cpp
#include <iostream>
using namespace std;

int main()
{
    for ( int count = 1; count <= 10; ++count )   // loop 10 times
    {
        if ( count == 5 )                         // if count is 5,
            continue;                             // skip remaining code in loop

        cout << count << " ";
    }
    cout << "\nUsed continue to skip printing 5" << endl;
}
```

**[Handwritten]**
- A box labelled **"count"** containing **1, 2, 3, 6**, with the values **1** and **2** crossed out. Arrows show the values moving through the loop.
- A curved arrow from the `if` line to the `++count` with the note **"count will not be executed"** [Uncertain: partly cut off at the edge of the slide]. The `cout` is skipped when `count` is 5.
- A red arrow from the `continue` to the increment, showing that the loop moves on to the next value.
- A mark **"count == 5"** beside the `if` line.
- The output written in a box at the bottom: **"O/P: 1 2 3 4 6 7 8 9 10"**, with the output lines shown across two rows.

*Output:*
```
1 2 3 4 6 7 8 9 10
Used continue to skip printing 5
```

*[Added]:* the value 5 is skipped, but the loop still counts it, because `count` is incremented before the test.

---

## 12. More Examples

### Slide 35: Example 5: sum the first n whole numbers
*Printed code:*
```cpp
int n;
cin >> n;
int total = 0;
for ( int value = 1; value <= n; value++ )
    total += value;
cout << "Total: " << total << endl;
```

*Explanation:* `total` collects the sum of 1 to `n`. For `n = 10`, the output is `Total: 55`. The formula n(n + 1)/2 gives the same result.

*Handwritten:* none.

### Slide 36: Example 6: find the largest entered value
*Printed code:*
```cpp
{
    int count;
    cin >> count;
    int value, largest = 0;

    for ( int i = 1; i <= count; i++ )
    {
        cin >> value;
        if ( value > largest )
            largest = value;
    }
    cout << "Largest: " << largest << endl;
}
```

*Explanation:* the program reads `count` values, one at a time. Each value is compared with `largest`, and the larger value replaces it.

*[Note]:* `largest` starts at 0. If every value entered is negative, the program reports 0, which is wrong. Start with the first value entered, or with the smallest possible value, to fix this.

*Handwritten:* none.

### Slide 37: Handwritten example with var and input
*[Handwritten]*

**Code (partly readable):**
```cpp
for ( int i = 0; i <= 2; i++ )
{
    cin >> input;
    if ( var > input )        // [Uncertain: the exact test is hard to read]
        var = input;
}
```

- The input values written above the loop: **2, 5, 4**.
- Two boxes drawn to the right: **var** holding **2**, and **inp** (input) holding **2**, with the variable **i** below. The value of `var` is circled.
- The lecturer appears to be tracing how `var` is updated from each input value. [Uncertain: the test and the final value of `var` are hard to read.]

*[Added]:* if the test is `var > input`, then `var` keeps the smallest value entered. With inputs 2, 5, 4, the result is 2. This is a common pattern for finding a minimum.

### Slide 38: Example 7: multiplication table
*Printed code:*
```cpp
int value;
cin >> value;
for ( int mul = 1; mul <= 10; mul++ )
{
    cout << value << " x " << mul << " = " << value * mul << endl;
}
```

*Example:* for input `7`, the output begins `7 x 1 = 7`, `7 x 2 = 14`, and ends `7 x 10 = 70`.

*Handwritten:* none.

### Slide 39: Example 8: separate the digits of a number
*Printed code:*
```cpp
int number;
cin >> number;
while ( number > 0 )
{
    int digit = number % 10;      // last digit
    cout << digit << " ";
    number /= 10;                 // remove last digit
}
```

*Example:* for input `1234`, the output is `4 3 2 1`, because the program takes the last digit first.

*[Added]:* this slide uses a `while` loop rather than a `for` loop, because the number of digits is not known in advance. The `%` operator gives the last digit, and `/=` removes it.

*Handwritten:* none.

---

## 13. Summary

1. **for header:** `for ( initialization ; condition ; increment )`. Each part sets up, tests, or updates the control variable.
2. **Optional parts:** the three expressions may be left out, but the two semicolons must stay.
3. **Common errors:** a semicolon right after the header (empty body), and a missing update (infinite loop).
4. **Steps:** use `++`, `--`, `+=`, or `-=` for steps other than 1. A negative step counts downward.
5. **Commas:** initialize or update several variables in one header, separated by commas.
6. **continue:** skips the rest of the body and goes to the next iteration. In a `for` loop, the update still runs.
7. **Examples:** counting, summing, finding the largest value, and digit separation are the common patterns. Check the start value, the test, and the update.

---

## Notes on Uncertain Items and Errors in the Slides
- Slide 4: the note "declaration" is partly cut off at the left edge.
- Slide 6: the first value in the box is hard to read, because it has been overwritten.
- Slide 7: the note "i < or <=, >?>=" is written as a question.
- Slide 12: the note "if removed, still OK" is partly cut off at the right edge.
- Slide 13: the note "can't be used for ≥ +1" is written as a bracket and is hard to follow.
- Slide 24: the `cout` line is not in braces, although it works because it is a single statement.
- Slides 29 and 30 are identical in the source.
- Slide 34: the note "count will not be executed" is partly cut off at the right edge.
- Slide 36: `largest` starts at 0, so the program gives the wrong answer when every value is negative.
- Slide 37: the test inside the loop and the final value of `var` are hard to read.
