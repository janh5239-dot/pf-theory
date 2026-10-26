# PF Labs 3 to 6 and Assignment No 1: What Is Covered

**Purpose:** an overview of the topics in each lab and in Assignment No 1. This file lists topics and requirements only. It does not contain solutions.
**Note:** Lab 2 is not included, because its task file was not provided.

---

## General Submission Rules

### Labs 3 to 6
- **AI or ChatGPT-generated code is marked as 0.**
- Create a Word file that contains both the **code** and the **screenshots of the input and output**. Both are required.
- Save the file as **"Your Name_Your ID"**.

### Assignment No 1
- Write the code in **Dev C++**, copy it, and paste it into **MS Word**.
- Upload the Word file to **Google Classroom**.

---

## Lab 3: Variables, Input and Output, Data Types

### Task 1: Program with comments and output
**Topics covered:**
- Writing comments, including the author's name ("Created by: ___").
- Declaring and initializing variables for a name, a semester, and a university name.
- Displaying the stored values with `cout`.

### Task 2: Name and age
**Topics covered:**
- Reading user input with `cin`.
- Displaying the input with `cout`.

### Task 3: Welcome event budget report
**Topics covered:**
- Choosing suitable data types for each input (text, whole numbers, decimal values).
- Reading several inputs with `cin`.
- **Implicit type conversion** when a calculation mixes data types.
- Formatting money values to **two decimal places** in the output.
- Displaying a labelled report.

---

## Lab 4: Arithmetic and Logical Operators

### Task 1: Student ID and arithmetic
**Topics covered:**
- Reading a value from the user.
- Assigning a value to a variable and applying the operators **addition, subtraction, multiplication, division, and modulus**.
- Displaying each result.

### Task 2: Expressions and operator precedence
**Topics covered:**
- Declaring three numbers and evaluating expressions that mix several operators.
- **Operator precedence:** which operator runs first in an expression.
- Writing comments that explain the order of evaluation and why it happens.

### Task 3: Relational and logical operators
**Topics covered:**
- Relational operators (`>`, `<`, `==`).
- Logical operators (`&&`, `||`, `!`).
- Printing the result of a logical expression. The task expects exactly one of the three expressions to be true.

---

## Lab 5: Decisions with if, else if, and Nested Conditions

### Task 1: ATM withdrawal system
**Topics covered:**
- Reading the account balance and the withdrawal amount.
- Checking for an invalid amount (zero or negative).
- Checking whether the amount is more than the balance.
- Checking divisibility with the **modulus operator** (multiples of 500).
- Choosing among several messages with `if`, `else if`, and `else`.
- Displaying the remaining balance after an approved withdrawal.

### Task 2: Online shopping discount
**Topics covered:**
- Choosing a discount based on a **range** of amounts.
- Rejecting negative input.
- Calculating the discount amount and the final payable amount.
- Ordering the range conditions correctly, from the highest range to the lowest.

---

## Lab 6: Range Checks and switch

### Task 1: Step counter
**Topics covered:**
- Declaring a single variable for the step count.
- Using `if`, `else if`, and `else` to choose a message from three ranges.
- Checking the boundaries of each range (for example, exactly 5000 and exactly 10000).

### Task 2: University cafeteria menu
**Topics covered:**
- Declaring a variable for the user's choice.
- The **`switch`**, **`case`**, **`break`**, and **`default`** statements.
- Displaying a message and price for each menu item.
- Handling an invalid choice in `default`.
- **Restriction:** this task must not use `if-else` statements.

---

## Assignment No 1

### Q1: Student information display
**Topics covered:**
- Displaying several lines of output with `cout`.
- Using **escape sequences**:
  - `\n` for a new line
  - `\t` for aligned columns
  - `\"` for quotation marks
  - `\\` for a backslash in a file path
- Placing a comment at the top of the program that contains a name.

### Q2: Game player profile output
**Topics covered:**
- Reproducing an exact text layout, including lines of dashes, aligned columns, quotation marks, and a row of stars.
- Combining `\t`, `\"`, `\\`, and `\n` to match the output exactly.
- The assignment requires the output to match the sample exactly.

### Q3: Find and correct the errors
**Topics covered:**
- Reading a short C++ program that contains several errors.
- Identifying **syntax errors**, such as a missing semicolon, missing quotation marks, and missing directives or keywords.
- Identifying errors in escape sequences and in the use of `cout` and `<<`.
- The task asks for three things: identify each error, explain what is wrong, and write the corrected program.

---

## Skills Summary

| Topic | Lab or assignment |
|---|---|
| Variables, `cin`, `cout`, data types | Lab 3 |
| Implicit type conversion, decimal formatting | Lab 3 |
| Arithmetic operators, precedence | Lab 4 |
| Logical and relational operators | Lab 4, Lab 5 |
| `if`, `else if`, `else` | Lab 5, Lab 6 |
| Modulus for divisibility | Lab 5 |
| Range checks and boundaries | Lab 5, Lab 6 |
| `switch`, `case`, `break`, `default` | Lab 6 |
| Escape sequences | Assignment Q1, Q2 |
| Finding and correcting syntax errors | Assignment Q3 |
