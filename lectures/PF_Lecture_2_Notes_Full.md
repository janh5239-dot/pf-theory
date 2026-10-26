# PF Lecture 2: Problem Solving, Algorithms, and the Path from Source Code to Execution

**Source:** Mod_PF_Lec_2_Sp_2026 (PDF)
**Instructor:** Engr. Dr. Alauddin
**Topic:** Programming fundamentals

**Legend**
- *Printed:* text from the original slide
- **[Handwritten]:** ink added by the lecturer
- **[Diagram]:** drawn figure, chart, or flow
- **[Uncertain]:** handwriting that is hard to read; the most likely meaning is given
- Slides 14, 23, and 25 have no slide number in the export. They are identified by their position in the deck.

---

## Table of Contents

1. Title (Slide 1)
2. Problem-solving steps (Slides 2 to 5)
3. Problem, logic, and algorithms (Slides 6 to 9)
4. Pseudocode and flowcharts (Slides 8 to 11)
5. From source code to executable (Slides 12 to 13)
6. Editors, source files, and IDEs (Slides 13 to 16)
7. Phase 2: Preprocessing (Slides 17 to 19, 25 to 28)
8. The math.h example (Slides 20 to 24)
9. Phase 3 to Phase 6: Compilation, linking, loading, execution (Slides 29 to 34)
10. Summary of tools (Slide 35)

---

## 1. Title

### Slide 1: Title
- *Introduction to Programming and Problem Solving*
- *Lecture 2 (Programming fundamentals), by Engr. Dr. Alauddin*

---

## 2. Problem-Solving Steps

### Slide 2: Steps for Problem Solving
*Printed:*
- Overall flow: **Problem → Analyze → Logic → Algorithm → Pseudocode/Flowchart → Code → Compile → Test → Debug/Refine**
1. **Problem:** clearly understand what needs to be solved and what result is required.
2. **Analyze:** identify the inputs, outputs, requirements, and constraints.
3. **Logic:** decide the logical steps and reasoning needed.
4. **Algorithm:** write a finite sequence of clear and ordered steps.
5. **Pseudocode / Flowchart:** represent the algorithm in simple English-like statements or graphical symbols before writing code.

**[Handwritten]**
- A small red mark and a short line above the flow arrow. It indicates emphasis on the flow.
- Beside step 2 (Analyze), a **× mark** and the word **"Limitation"**. This means that the constraints in step 2 are the limitations of the problem, such as the restrictions the solution must respect.

### Slide 3: Steps for Problem Solving (Contd.)
*Printed:*
6. **Code:** convert the pseudocode or flowchart into a language such as C, C++, Java, or Python.
7. **Compile:** translate the C/C++ source code into machine-executable form and find syntax or compilation errors.
8. **Test:** run the program with different inputs and compare actual output with expected output.
9. **Debug / Refine:** find and correct errors and improve correctness, efficiency, or readability.

**[Handwritten]**
- An arrow pointing at step 8 (Test), with the note **"Removing errors."** Testing finds errors, and debugging removes them.

### Slide 4: Table of the Nine Steps
*Printed:* a table with three columns (Step, What We Do, Purpose).

| Step | What We Do | Purpose |
|---|---|---|
| 1. Problem | Understand what needs to be solved | Clearly define the problem |
| 2. Analyze | Identify inputs, outputs, requirements, constraints | Understand the problem completely |
| 3. Logic | Decide how the problem can be solved logically | Develop the basic solution idea |
| 4. Algorithm | Write the solution as ordered steps | Create a systematic solution |
| 5. Pseudocode / Flowchart | Represent the algorithm with simple statements or symbols | Make the solution easy to understand before coding |
| 6. Code | Convert the solution into a language such as C++ | Create the actual program |
| 7. Compile | Translate the C++ program and check for compilation errors | Convert the program to executable form |
| 8. Test | Run the program with different inputs | Check whether results are correct |
| 9. Debug / Refine | Find and correct errors, improve the program | Make the program correct and reliable |

*Handwritten:* none.

### Slide 5: Important
*Printed:*
- A weak approach is to start writing code immediately.
- A strong approach is to first understand the task, inputs, processing, output, and logic.
- Code is only one stage of the solution.

*Handwritten:* none.

---

## 3. Problem, Logic, and Algorithms

### Slide 6: Problem and Logic
*Printed:*
- **Logic** means the reasoning or method used to solve the problem.
- **Example problem:** determine whether a student has passed or failed. Passing marks = 50.
- **Logic (plain form):** IF marks ≥ 50, the student passes; ELSE, the student fails.
- **C++ expression (for later):**
  ```cpp
  if (marks >= 50) {
      cout << "Pass";
  } else {
      cout << "Fail";
  }
  ```

*Handwritten:* none.

### Slide 7: What is an Algorithm?
*Printed:*
- A clear, finite, step-by-step solution.
- An algorithm is a finite, ordered, and unambiguous sequence of steps used to solve a problem.
- **Example:** Add two numbers.
  1. Start
  2. Input first number
  3. Input second number
  4. Add both numbers
  5. Store result
  6. Display result
  7. Stop

**[Handwritten]**
- An arrow pointing at the word "unambiguous" in the definition, labeled **"no doubts."** An algorithm must leave no room for interpretation.
- Beside the steps: **"* No syntax."** The algorithm does not use any programming syntax.
- Beside the steps, underneath: **"* No rules."** The algorithm has no language rules, since it is plain steps.

### Slide 8: What is Pseudocode?
*Printed:*
- English-like representation of an algorithm.
- Helps write logic in a structured form without worrying about exact C++ syntax.
- Easy to understand, program-language independent, focuses on logic, easy to convert into code, and helps find logical errors early.
- **Example:**
  ```
  BEGIN
  INPUT A
  INPUT B
  SUM = A + B
  PRINT SUM
  END
  ```

**[Handwritten]**
- At the bottom: **"* Again: no rules / syntax."** The lecturer stresses that pseudocode, like the algorithm, has no fixed syntax or rules.

### Slide 9: Algorithm → Pseudocode → C++ Program
*Printed:*
- The same solution in three forms: the algorithm (numbered steps), the pseudocode (BEGIN to END), and the C++ program.
- **C++ program:**
  ```cpp
  #include <iostream>
  using namespace std;

  int main() {
      int A, B, SUM;
      cin >> A >> B;
      SUM = A + B;
      cout << SUM;
      return 0;
  }
  ```

*Diagram:* three boxes connected by arrows, from the algorithm to the pseudocode to the C++ program.

*Handwritten:* none.

---

## 4. Pseudocode and Flowcharts

### Slide 10: Flowcharts
*Printed:*
- A visual form of the algorithm. Flowcharts help students see the order of execution clearly.

*Diagram: legend of flowchart symbols*
- **Terminator** (rounded rectangle, purple): start and end of a program, with the keywords BEGIN and END.
- **Process** (rectangle): an instruction to be carried out.
- **Arrow:** shows the flow of the algorithm pathways.
- **Decision** (diamond, blue): splits the flow into multiple paths for **selection** and **repetition**.
- **Input / Output** (parallelogram, orange): data entry by the user or display of data by the program.
- **Subprogram** (rectangle with side bars, dark blue): references another program within the program.

*Handwritten:* none.

### Slide 11: A Simple Flowchart
*Printed:*
- Representing a process for dealing with a non-functioning lamp.

*Diagram: flowchart with the following steps:*
1. Start: "Lamp doesn't work"
2. Decision: "Lamp plugged in?"
   - No → "Plug in lamp"
   - Yes → go to step 3
3. Decision: "Bulb burned out?"
   - Yes → "Replace bulb"
   - No → "Repair lamp"

*Handwritten:* none.

---

## 5. From Source Code to Executable

### Slide 12: From C++ Source Code to Executable Program
*Printed:*
- The CPU does not directly understand C++.
- The compiler translates C++ into lower-level instructions. The linker connects the required libraries and creates the final executable.

*Diagram: pipeline*
**Source Code (.cpp file) → Preprocessor → Compiler → Object Code → Linker → Executable → CPU**

**[Handwritten]**
- Beside the first bullet: an arrow pointing to **"program / software"**. A C++ program is software that the CPU cannot read directly.
- Beside the title: a bracket and the words **"Ready to be run by PC"** [Uncertain: the last word may be "PC" or "CPU"]. Another note reads **"(exe / actual code)"**, which means the executable is the actual machine code that is ready to run.
- A bracket on the right of the compiler and linker bullet, grouping them as the translation steps.
- Arrow above the Compiler box, labeled **"Compilation."**
- Arrow below the Preprocessor box, labeled **"pre processing."**
- Arrow below the Linker box, labeled **"linking."**

### Slide 13: Phase 1: Creating a Program
*Printed:*
- Phase 1 consists of editing a file with an editor program, normally known simply as an editor.
- You type a C++ program (source code) with the editor, make any corrections, and save the program on a secondary storage device such as your hard drive.

**[Handwritten]**
- A bracket and arrow near the bottom: **"(Primary storage device / Main memory RAM)."** The note is placed beside the text about saving to secondary storage. It sets out the contrast: while editing, the program is held in primary memory (RAM), and it is saved to secondary storage (the hard drive) afterward.

---

## 6. Editors, Source Files, and IDEs

### Slide 14: Source File Names and Editors (unnumbered in export)
*Printed:*
- C++ source code filenames often end with the **.cpp** extension, which indicates that the file contains C++ source code.
- Two editors widely used on Linux systems are **vim** and **emacs**.
  - Linux is an operating system (like Windows).
  - Other operating systems include Mac, Android, iOS, and so on.
- C++ software packages for Microsoft Windows, such as Microsoft Visual C++, have editors integrated into the programming environment.

*Handwritten:* none.

### Slide 15: Text Editors and IDEs
*Printed:*
- You can also use a simple text editor, such as Notepad in Windows, to write your C++ code.
- For organizations that develop substantial information systems, **integrated development environments (IDEs)** are available, designed by software companies.

**[Handwritten]**
- An arrow from "integrated" to the note **"software"** (the IDE is a software package), and a note beside it, partly cut off, that reads **"comb..."** [Uncertain: probably "combined," meaning several tools are combined in one package].
- Below the slide, the lecturer wrote: **"Integration → to combine / gather / collect."** This explains the word "integrated" in IDE.

### Slide 16: IDEs
*Printed:*
- IDEs provide tools that support the software-development process, including editors for writing and editing programs, and **debuggers** for locating logic errors.
- Popular IDEs include Microsoft Visual Studio 2010 Express Edition, Dev C++, NetBeans, Eclipse, and CodeLite.

**[Handwritten]**
- At the top, an arrow to a word in Urdu meaning "means," with the note **"means / software."** [Uncertain: the Urdu word is likely "ذریعہ" (means)]. So an IDE is a means (a software tool).
- A bracket beside "software-development process," labeled **"software program."**
- Underline under **"debuggers,"** which marks the key tool.
- Underline under **"Eclipse."**

---

## 7. Phase 2: Preprocessing

### Slide 17: Phase 2: Preprocessing a C++ Program
*Printed:*
- A preprocessor is a software component that processes C++ source code before the compiler performs compilation.
- So preprocessing is Phase 2 and compiling is Phase 3.
- The C++ preprocessor follows commands called **preprocessor directives**. These tell the compiler that certain changes are to be made to the program before compilation.

**[Handwritten]**
- Arrow at the title pointing to **"inside IDE / compiler."** The preprocessor works inside the IDE or compiler environment.
- A downward arrow to the word "preprocessor directives," with **#include <iostream>** written below it and a check mark. The `#include` line is a preprocessor directive.

### Slide 18: Phase 2 (contd.)
*Printed:*
- The preprocessor handles directives that begin with `#`, such as `#include` and `#define`.
- Example: `#include "math.h"` tells the preprocessor to insert or copy the entire contents of the header file "math.h" into the source code.
- The preprocessor's main purpose is to prepare the source code for the compiler.

*Handwritten:* none.

### Slide 19: Phase 2 (contd.), Example with math.h
*Printed:*
- Code example:
  ```cpp
  #include "math.h"
  int main() {
      int x = add(5, 3);
  }
  ```
- **Note:** math.h is a user-defined library (defined by the user) and not a standard library file.
- **Keyword:** reserved words whose meaning is already known to the compiler.
- **abc.h:** the .h extension represents a header file.

**[Handwritten]**
- A curved arrow linking the word "keyword" to the `add(5, 3)` line, with a short note above it [Uncertain: the handwriting is hard to read; it probably says "keyword" or "is defined in the header"].
- Arrow from `#include "math.h"` to the note **"it has all the information about add()"**. The header declares what add() looks like.
- A bracket beside the note, labeled **"preprocessor directive."**

---

## 8. The math.h Example

### Slide 20: Two Kinds of Header Files (handwritten only)
**[Handwritten]**
- **(1) `"math.h"`:** used in our example. It is a **user-defined** file, not a standard library header.
- **(2) `<math.h>` or `<cmath>`:**
  - `math.h` was used in the C language. It can also be used in C++ as well.
  - `<cmath>` is a **better alternative in C++** (the C++ version of the header).
- Highlights on "used in our example," "is user-defined," and "(not std. library headerfile)."

### Slide 21: Example of "math.h"
*Printed:*
- Suppose we have a user-defined header file named `math.h`, which contains the declaration (necessary information) of an `add()` function (a piece of code with a specific name and task used in the source code).
- Note: the standard library header `<math>` does not have an `add()` declaration.
- The actual implementation (the code) is placed in a separate file named `add.cpp`, defined by the user.

*Handwritten:* none.

### Slide 22: Example of "math.h" (contd.)
*Printed:*
- When `main.cpp` (our program) contains `#include "math.h"`, the preprocessor attaches or inserts the statements from `math.h` into `main.cpp`.
- The actual code for `add()` is available in a user-defined `add.cpp`.
  - This code will be compiled later in the compilation phase, and linked with `main.cpp` by the **linker** in the linking phase.

*Handwritten:* none.

### Slide 23: Example of math.h (unnumbered in export)
*Diagram: three panels*
- **main.cpp (source code):**
  ```cpp
  #include "math.h"
  int main() {
      int x = add(5, 3);
  }
  ```
- **math.h (header file):** `int add(int, int);`
- **add.cpp (actual code for add()):**
  ```cpp
  int add(int a, int b) {
      return a + b;
  }
  ```

**[Handwritten]**
- A note with an arrow to math.h: **"Not a standard library file."**
- A note beside the header: **"only in formation"** [Uncertain: "only information," meaning the header holds only the declaration, not the implementation].
- An arrow to add.cpp, labeled **"User defined."**
- Underline under **"Actual code for add()."**
- Quotation marks written around "math.h" at the top right, with **"or <math>"** beside them. The two ways of writing the include are shown.

### Slide 24: Header Forms (handwritten only)
**[Handwritten]**
- **`<math>`** → standard library header file.
- **`"math.h"`** → may be a user-defined file, or a standard library file.
- This explains the difference between the two include forms. Angle brackets usually point to the system (standard) library. Quotes usually point to a file in the project (user-defined).

### Slide 25: What Does #include Actually Do? (unnumbered in export)
*Printed:*
1. The `#include` directive is a preprocessor directive, not a linker instruction.
2. For a header such as `math.h`, preprocessing conceptually inserts the header's contents at the `#include` location.
3. Therefore, this code:
   ```cpp
   #include "math.h"
   int main() {
       int x = add(5, 3);
   }
   ```
   can be viewed, conceptually after preprocessing, as:
   ```cpp
   int add(int, int);
   int main() {
       int x = add(5, 3);
   }
   ```

*Handwritten:* none.

### Slide 26: Phase 2: Example of "iostream.h"
*Printed:*
- A program with `#include <iostream>` and a statement using `cout`.
- `<iostream>` is a standard C++ header file that provides the information required for input and output (cout and so on).
- When the preprocessor reads `#include <iostream>`, it copies or inserts the contents and statements of the iostream header into the source.

*Code shown:*
```cpp
#include <iostream>
int main()
{
    cout << "Hello";
}
```

*Handwritten:* none.

### Slide 27: Phase 2: Example of "iostream.h" (contd.)
*Printed:*
- Conceptually, we can think of this as replacing the `#include` line with the contents of the header.

*Handwritten:* none.

### Slide 28: Phase 2: Example of "iostream.h" (contd.)
*Printed:*
```
#include <iostream>
↓
Preprocessor
↓
Source file now has the relevant iostream declarations/information/text
↓
Compiler
```

**[Handwritten]**
- Arrow beside `#include <iostream>` with the note **"A file → header file → it has information about i/p, o/p instructions."** The iostream file is a header containing input and output information.
- Arrow beside "Preprocessor," labeled **"appended / attached: the header with source code."** The header is attached to the source code.

---

## 9. Phases 3 to 6: Compilation, Linking, Loading, Execution

### Slide 29: Phase 3: Compilation
*Printed:*
- Compiler: an application program.
- It translates C++ into machine language code (object code).
- It also reports syntax errors.
- Its output is an object file (*.obj or *.o), for example `add.obj`.

*Handwritten:* none.

### Slide 30: Phase 3: Compilation (contd.)
*Printed:*
- `main.cpp` is compiled into `main.o` or `main.obj`.
- Similarly, `add.cpp` is compiled separately into `add.o` or `add.obj`.

*Diagram:*
```
main.cpp ──Compiler──> main.obj
add.cpp  ──Compiler──> add.obj
```

*Handwritten:* none.

### Slide 31: Phase 4: Linking
*Printed:*
- A linker links the object code of the source file with the code for the referenced functions to produce an executable program.
- If the program compiles and links correctly, an executable program is produced.

*Diagram:*
```
main.cpp ──compilation──> main.obj
add.cpp  ──compilation──> add.obj
main.obj + add.obj ──Linking──> Executable File
```

*Handwritten:* none.

### Slide 32: Phase 5: Loading
*Printed:*
- Before a program can be executed, it must first be placed in memory (RAM).
- The loader takes the executable image from secondary storage (hard disk) and transfers it to memory.
- Additional components from shared libraries that support the program are also loaded.

*Handwritten:* none.

### Slide 33: Phase 5: Loading (diagram)
*Diagram:* a disk at the bottom, an arrow up into a **Loader** box, and an arrow from the Loader into a **Primary Memory** block. The caption reads "Phase 5: Loader puts program in memory."

*Handwritten:* none.

### Slide 34: Phase 6: Execution
*Printed:*
- The final program is machine code, ready for execution by the processor.
- The CPU executes one instruction at a time.
- Some modern computer architectures can execute several instructions in parallel.

*Handwritten:* none.

### Slide 35: Tools Summary (handwritten only)
**[Handwritten]**
- A bracket grouping the list: **"preprocessor, compiler, linker, loader"** (each marked with an asterisk).
- The bracket is labeled **"Application programs inside IDE."** So the preprocessor, compiler, linker, and loader are all application programs that run inside the IDE.

---

## Overall Summary

1. **Problem-solving path:** Problem → Analyze → Logic → Algorithm → Pseudocode/Flowchart → Code → Compile → Test → Debug.
2. **Algorithm:** a finite, ordered, unambiguous sequence of steps. It has no syntax.
3. **Pseudocode:** English-like, language-independent, and close to code, but still without strict syntax.
4. **Flowchart:** a visual form of the algorithm, using symbols such as terminators, processes, decisions, and input/output.
5. **Build pipeline:** Source (.cpp) → Preprocessor → Compiler (object .obj/.o) → Linker (executable) → Loader (RAM) → CPU execution.
6. **Preprocessor:** handles `#` directives, such as `#include`, by inserting header contents into the source file.
7. **Header files:** `"file.h"` may be user-defined. `<file>` usually refers to a standard library. `<cmath>` is the C++ alternative to `math.h`.
8. **IDEs:** integrated tools (editor, debugger, and the build programs) that support the full development process.

---

## Notes on Uncertain Items
- Slide 12: the phrase "Ready to be run by PC" [the last word may be "PC" or "CPU"].
- Slide 15: the partly cut-off word "comb..." [probably "combined"].
- Slide 16: the Urdu word beside the top arrow [probably "ذریعہ," meaning "means"].
- Slide 19: the note beside the curved arrow to add(5, 3) is hard to read.
- Slide 23: "only in formation" [probably "only information"].
