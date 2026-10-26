# PF Lecture 1: Introduction to Programming and Problem Solving

**Source:** Mod_PF_Lec_1_Sp_2026 (PDF, 22 slides)
**Instructor:** Engr. Dr. Alauddin
**Topic:** Programming fundamentals

**Legend**
- *Printed:* text from the original slide
- **[Handwritten]:** red or other ink added by the lecturer
- **[Diagram]:** drawn figure or chart
- **[Uncertain]:** handwriting that is hard to read; the most likely meaning is given

---

## Table of Contents

1. Basics: computer, program, hardware, software (Slides 2 to 3)
2. Why computers need programming (Slides 4 to 5)
3. Why programming matters (Slides 6 to 7)
4. Programming languages and syntax vs logic (Slides 8 to 9)
5. Computer language levels (Slides 10 to 13)
6. Analog vs digital and HDL (Slides 14 to 19)
7. Machine language vs hardware language (Slides 20 to 21)
8. Assembler, compiler, and synthesis tool (Slide 22)

---

## 1. Basics

### Slide 1: Title
- *Introduction to Programming and Problem Solving*
- *Lecture 1 (Programming fundamentals), by Engr. Dr. Alauddin*

### Slide 2: What is a Computer?
*Printed:*
- **Computer:** a device that performs computations (mathematical operations etc.) and logical operations. It is a machine that processes data according to a list of instructions, and a programmable device that can store, retrieve, and process data.
- **Computer programs:** sets of instructions that control a computer's processing of data.
- **Hardware:** the physical parts of a computer (keyboard, screen, mouse, disks, memory, CD-ROM, processing units).
- **Software:** a collection of computer programs that perform specific tasks on a computer system. Software is the programs that run a computer.

**[Handwritten]**
- Beside the title: **"Instructions / statements → what to do?"** with an arrow. The lecturer is saying that a computer works on instructions (statements) that tell it what to do.
- Beside "logical operations": **"(AND / OR etc.)"**
- Beside "mathematical operations": **"+ , − , × , ÷"**, showing the arithmetic operators.
- Underlines under **"programmable"** and **"store, retrieve"**, with a note **"↳ load / fetch"** [Uncertain: the word may be "load" or "fetch"]. Store and retrieve correspond to memory operations (load and fetch).
- Highlight on **"A programmable"** (yellow).
- Under "Sets of instructions" a bracket and arrow pointing up at "programs."
- Chain written near Hardware and Software: **"instructions → program → software."** This shows the hierarchy: instructions make a program, and programs make up software.
- Beside "Software": **"(program)"** with an arrow, confirming that software means programs.

### Slide 3: What is Programming?
*Printed:*
- Programming is the process of writing a set of instructions that tells a computer how to perform a specific task.
- These instructions are written in a programming language such as C, C++, Java, or Python.
- Programming helps solve problems, automate tasks, and develop software applications.
- Examples: add two numbers, calculate a grade, control a robot, process a bank transaction, detect an object in an image.

*Handwritten:* none.

---

## 2. Why Computers Need Programming

### Slide 4: Why Does a Computer Need Programming?
*Printed:*
- A computer cannot decide what to do by itself. It needs instructions from a programmer.
- Programming tells the computer how to process data and produce the required results.
- Programming allows computers to perform complex tasks quickly and accurately.

*Handwritten:* none.

### Slide 5: Why Does a Computer Need Programming? [contd.]
*Printed:*
- **Automation:** computers can repeat tasks without continuous human intervention.
- Programming converts human solutions into computer-executable instructions.
- **Example:** to calculate a student's average marks, write a program that does the following: input marks → add them → divide by the number of subjects → display the average.

**[Handwritten]**
- Underline under **"executable"**, with an arrow above it.
- Beside "human solutions": **"ready (to) run by"** [Uncertain: the note is partly cut off at the margin]. Its meaning: the human solution is turned into something the machine can run directly.
- Next to the example: a bracket and a note in parentheses. It is cut off, so its content cannot be read.
- Beside "automation": Urdu handwriting [Uncertain: most likely a translation of "automatic" or "خودکار"]. This is the lecturer's own translation for the class.

---

## 3. Why Programming Matters

### Slide 6: Why is Programming Important?
*Printed:*
- **Solves problems:** develop step-by-step solutions to real-world problems. Example: calculating students' grades and final results.
- **Automates tasks:** repetitive work is done automatically, saving time and effort. Example: a payroll program computes salaries.
- **Develops software:** almost all computer and mobile applications are built with programming. Examples: web browsers, mobile apps, games.

*Handwritten:* none.

### Slide 7: Why is Programming Important? [contd.]
*Printed:*
- **Improves efficiency:** programs process large amounts of data quickly and accurately. Example: a university system processes thousands of student records in seconds.
- **Enables innovation:** programming helps create new technologies and intelligent systems. Examples: AI, robotics, self-driving cars, IoT devices.

**[Handwritten]**
- Arrow pointing at the word **"Enables Innovation"** with a note in Urdu [Uncertain: the note reads like "نئی" (new), which fits the idea of innovation].
- At the bottom: **"↳ Internet of Things (Everything is connected to Internet)."** This explains IoT, which is the last example on the slide.

---

## 4. Programming Languages, Syntax, and Logic

### Slide 8: What is a Programming Language?
*Printed:*
- A language humans use to give instructions to a computer.
- A computer cannot understand normal human language directly.
- Programmers therefore use special languages to write instructions. These tell the computer what task to perform and how to perform it.
- Examples: C, C++, Java, Python, JavaScript.
- Each language has its own rules for writing instructions.

**[Handwritten]**
- Next to the title, with an arrow: **"A mean/medium of conveying your instructions to computer."** This means a programming language is a medium for conveying instructions to the computer.

### Slide 9: Syntax and Logic (fully handwritten, no printed text)
**[Handwritten]**
- **"Syntax: A specific way of writing a program."**
  - Example written on the slide: `cout << "abc";`
  - Note: the syntax is different for every language.
- **"Logic: Concepts → same."**
  - Examples given: **condition** and **loop**.
  - Note: logic concepts are the same in every language, but syntax is different.

**Summary:** Syntax is the grammar of a language, and logic is the idea behind the code. Learning logic lets you move between languages. Learning syntax is specific to each language.

---

## 5. Computer Language Levels

### Slide 10: Computer Languages (Low and Middle Level)
*Printed:*
- Computer languages are divided into three types.
- **Low-level (machine) languages:** machine dependent. They use groups of numbers giving machine-specific instructions. Example: `+1300042774`, `+1400593419`, `+1200274027`.
- **Middle-level (assembly) languages:** English-like abbreviations for basic computer operations, translated by assemblers. Example: `LOAD BASEPAY`, `ADD OVERPAY`, `STORE GROSSPAY`.
- Translator programs called **assemblers** convert assembly programs to machine code at computer speed.

**[Handwritten and diagrams]**
- Circled **"1"** next to low-level and **"2"** next to middle-level.
- Arrow from low-level pointing to: **"need help of compiler / software near to machine understandable standard."** The meaning is that machine language is close to the hardware, so it is hard for humans to read, and it needs a translator.
- Arrow to the numbers: **"decimal / binary."** The numbers are the machine code, shown in decimal form but stored as binary.
- A blue arrow from the middle-level section to a handwritten note: **"Transistors can be used as switch (ON/OFF)."** The note links the idea of machine code to the transistor switch behavior from Slide 16.
- A bracket beside the assembly example with the note **"More human understandable standard."**
- Beside the assembly example: **"English-like instructions"** (handwritten, with an arrow).
- Highlight on **"assembler"** and on **"machine code / language programs at computer speed."**

### Slide 11: Handwritten Summary (no printed text)
**[Handwritten]**
- **"High level compiler → machine level (0's / 1's)."**
- **"Assembly code → [Assembler (convert to)] → Machine lang (Binary)."**
- **"* More information about the hardware are required for assembly language because we program hardware directly."**
- The handwritten note is the lecturer's explanation of why assembly needs more hardware knowledge than high-level languages.

### Slide 12: Handwritten Explanation (no printed text)
**[Handwritten]**
- **"ADD A, B → You need to know what is A & B."**
  - Meaning: an assembly instruction needs the programmer to know exactly what the operands are and where they are stored.
- **"* In high level languages we do not need hardware details."**
- **"Simulator: Run / Test a physical scenario as a software known as simulator."**
  - Meaning: a simulator is software that runs or tests a physical scenario, so it can be checked without real hardware.

### Slide 13: Computer Languages (High-Level)
*Printed:*
- **High-level languages:** similar to everyday English, use mathematical notation, translated via compilers.
- **Example:** `grossPay = basePay + overTimePay`
- **C and C++** are the most widely used high-level languages.
- Other examples:
  - **FORTRAN** (formula translator): scientific and engineering applications.
  - **COBOL** (common business oriented language): manipulating large amounts of data.
  - **Pascal:** teaching structured programming.
- Translator programs called **compilers** convert high-level programs into machine language.

**[Handwritten]**
- Arrow beside the heading: **"No hardware details are required."**

---

## 6. Analog vs Digital and HDL

### Slide 14: HDL
*Printed:*
- HDL is "a language for describing/designing digital hardware," rather than being simply a low-level programming language.

**[Handwritten]**
- Note beside the definition: **"that can store digital values."**
- **"Analog: Real-world data is analog."**
  - Examples: sound, image, air.
  - **"Continuous values: it has infinite values between two points."**

### Slide 15: Analog vs Digital (fully handwritten, with diagrams)
**[Diagram: Analog]**
- A continuous wavy sine curve drawn over a time axis. It is smooth, with no gaps.

**[Diagram: Digital]**
- A stepped signal with discrete levels, drawn beside the analog curve. The values jump between levels, so it is not a smooth curve.
- The levels are labeled **1, 2, 3** on an axis, which shows discrete steps.
- A small axis with the points **1** and **2** marked, showing that there are no points between them in the digital system.

**[Handwritten notes]**
- **"Digital → discrete / specific / discontinuous."**
- **"Finite values between any two points."**
- **"usually 0s & 1s"** (in a bracket)
- **"* Memory is finite."** This is a key reason digital systems use a limited set of values.

**Summary table (reconstructed from the notes):**

| | Analog | Digital |
|---|---|---|
| Values | Continuous, infinite between two points | Discrete, finite between two points |
| Examples | Sound, images, air | Computer data stored as 0s and 1s |
| Memory | Not relevant | Finite |

### Slide 16: Hardware Description Languages (HDL), Functionality Order
*Printed:*
- Computer functionality order: **Transistors → Logic Gates → Flip-Flops → Registers → ALU → CPU.**
- A transistor works like a tiny electronic switch (ON/OFF).
- Combining transistors builds logic gates: AND, OR, NOT.
- Logic gates combine to build flip-flops, which store bits.
- Flip-flops and logic gates form registers, ALUs, control circuits, memory, and processors.
- Modern CPUs and memory chips contain billions of transistors.

*Handwritten:* none. The slide is clean, so the content is the same as the printed text.

---

## 7. HDL Details

### Slide 17: HDL [contd.]
*Printed:*
- An HDL describes the structure and behavior of digital hardware circuits: transistors, flip-flops, registers, RAM, ALU, and so on.
- Machine language tells an existing CPU what to do. HDL describes what the hardware should do or how it should be designed.

*Handwritten:* none.

### Slide 18: HDL [contd.]
*Printed:*
- Machine language is executed by the processor. An HDL description is processed by synthesis tools to produce hardware logic.
- A **synthesis tool** is software that converts an HDL program, written in Verilog or VHDL, into a hardware circuit design that can be implemented in hardware.

**[Handwritten]**
- Yellow highlight on **"tool is software"**.
- Bracket under the words **"Verilog & VHDL"** with the note **"languages."** So Verilog and VHDL are the languages, and synthesis tools are the software.

### Slide 19: HDL Tools
*Printed:*
- Commonly used tools: Xilinx Vivado, Intel Quartus Prime, Synopsys Design Compiler, Cadence Genus.
- Verilog and VHDL describe hardware. Synthesis tools are software programs that convert these descriptions into hardware logic.

*Handwritten:* none.

---

## 8. Machine Language vs Hardware Language

### Slide 20: Machine Language (ML) vs Hardware Language
*Printed:*
- ML tells an existing processor what operation to perform, such as addition, subtraction, or data movement.
- Machine language is hardware-dependent because different processors have different instruction sets. For example, x86 and ARM processors use different machine-language instructions.

**[Handwritten]**
- Highlights on **"existing"**, **"x86 processor"**, and **"ARM"**.
- Note: **"x86 & ARM → processor family / models."** So x86 and ARM are processor families, and each family has several models.

### Slide 21: Machine Language vs Hardware Language (contd.)
*Printed:*
- Machine language is closely related to hardware, but it does not describe, create, or redesign the hardware itself.
- **Therefore**, machine language should be called a low-level programming language, not a hardware description language.

*Handwritten:* none.

---

## 9. Assembler, Compiler, and Synthesis Tool

### Slide 22: Assembler vs Compiler vs Synthesis Tool
*Printed:*
- Assembly language → **Assembler** → Machine code → CPU executes it.
- C/C++ → **Compiler** → Machine code → CPU executes it.
- Verilog/VHDL → **Synthesis tool** → Hardware logic → Hardware (blocks containing flip-flops, logic blocks, and so on).

**[Handwritten]**
- Arrow above the first two lines, labeled **"languages."**
- Arrow pointing to the synthesis line, labeled **"software."**
- This marks the difference: the assembler and compiler are software that translates languages, and the synthesis tool is software that produces hardware.

**Comparison (from slide content):**

| Input | Tool | Output | Executed by |
|---|---|---|---|
| Assembly | Assembler | Machine code | CPU |
| C / C++ | Compiler | Machine code | CPU |
| Verilog / VHDL | Synthesis tool | Hardware logic | Becomes the hardware |

---

## Overall Summary

1. A **computer** runs **instructions** grouped into **programs**, which make up **software**.
2. **Programming** means writing instructions in a **language** the computer can follow. The computer cannot decide on its own.
3. **Languages come in three levels:** machine (numbers, close to hardware), assembly (abbreviations, translated by an **assembler**), and high-level (English-like, translated by a **compiler**).
4. **Syntax** is language-specific, while **logic** (conditions, loops) is the same across languages.
5. **Analog** data is continuous, and **digital** data is discrete (0s and 1s). Memory is finite.
6. **HDLs** (Verilog, VHDL) describe hardware. **Synthesis tools** turn those descriptions into circuits. Machine language is not an HDL, since it runs on existing hardware and does not design it.
7. Hardware is built in layers: transistors → logic gates → flip-flops → registers → ALU → CPU.

---

## Notes on Uncertain Items
- Slide 2: the word after "Store, retrieve" is "load / fetch" [Uncertain].
- Slide 5: the Urdu note by "automation" and the partly cut-off note "ready (to) run by" [Uncertain].
- Slide 5: the note beside the example is cut off at the margin and could not be read.
- Slide 7: the Urdu note by "Enables Innovation" [Uncertain].
- Slide 15: the diagram labels and axis values are small and approximate.
