# Memory Safety Attacks

![License](https://img.shields.io/badge/license-MIT-blue.svg)  
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)

## Table of Contents

- [About](#about)
- [Tools Used](#tools-used)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Lab](#lab)
    - [Buffer Overflow to Shellcode](#buffer-overflow-to-shellcode)
    - [Side Effects of a Buffer Overflow](#side-effects-of-a-buffer-overflow)
- [Usage](#usage)
    - [Disclaimer](#disclaimer)
- [Contact](#contact)
- [Acknowledgments](#acknowledgments)
- [License](#license)

---

## About

Lab related to memory safety in C. The emphasis in this lab continued to be on understanding low level code. Unlike the previous two labs this lab moved on from identifying the vulnerabilities and was more concerned with the later stages of an attack.<br>

The GNU project debugger (GDB) continues to be useful for this lab. If you are reading this and are in need of a refresher check out this [GDB manual](https://sourceware.org/gdb/current/onlinedocs/gdb.html/index.html). You can also use the help command while GDB is running.

---

## Tools Used

- **Operating System**: Linux x86-64. Recommended to use a machine running Ubuntu 22.04.
- **Programming Language(s)**: C, Perl, Python, Shell
- **Tools**: The GNU Project Debugger (GDB), objdump

---

## Getting Started

### Prerequisites

- A machine running Ubuntu 22.04. The program should on most recent Linux systems, although the supported configuration is Ubuntu 22.04.
- C. The entire project was written using C programming language.
- (Optional) Perl. Optional but useful for scripting.
- (Optional) Python. Optional but useful for scripting.
- The file overflow-from-file.c. Available under src.
- The file overflow-from-file-2.c. Available under src.
- (Optional) The precompiled binary overflow-from-file. Available under src.
- (Optional) The precompiled binary overflow-from-file-2. Available under src.
- The GNU Project Debugger (GDB).
  
### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/JackTschetter/memory-safety-attacks
   cd memory-safety-attacks

This repository contains the source files overflow-from-file.c, overflow-from-file-2.c. The repository also contains the precompiled binaries overflow-from-file, and overflow-from-file-2. Suggested to use the precompiled binaries provided, although I did not require this of my students, but it makes the lab much easier.<br>

**Note** This lab was designed and the binaries are compiled for Linux x86-64. It is strongly reccommended to use a machine running Ubuntu 22.04. If you are using a different Linux x86-64 distribution that might also work, but has not been tested. Other Unix style x86-64 systems might also work, but with significant difficulties.<br>

For anyone interested the Linux x86-64 command used to compile the binary was<br>

**gcc -no-pie -z execstack -g -Wall -fno-stack-protector overflow-from-file.c -o overflow-from-file**

The GCC options -no-pie, -z execstack, and -fno-stack-protector are all disabling defensive mechanisms. -z execstack disables W xor X with respect to the stack, making the stack executable as well as writable. -no-pie, disables positional execution, and -fno-stack-protector turns off the stack protector.<br>

${\color{red}WARNING}$ This is intentionally vulnerable low level code and source code that deliberately ignores software engineering best practices. These files were created for the sole purpose of teaching a class on Designing and Developing Secure Software. The command used to compile the binaries does so in a way that intentionally disables various defense mechanisms against certain kinds of attacks. Exercise enhanced caution when downloading and using the provided code.

---

## Lab

### Buffer Overflow to Shellcode

### Side Effects of a Buffer Overflow

---

## Usage

This project was created for the purposes of teaching the class Designing and Developing Secure Software at UMN Twin Cities. For teaching purposes we provided students in the course the same source code, sample images, and pre compiled binary available for download from this repo. 

The source code is deliberately buggy and does not follow software engineering best practices. In particular their were 4 vulnerabilities which were deliberately planted in the BCIMGVIEW.c source. The goal of this assignment was for students to discover, exploit and mitigate at least 3/4 of the planted vulnerabilities. 

To help with this I regularly held labs, and office hours to assist the students. The goal of this project was to teach core competencies such as code auditing, strategies to audit large code bases, and heuristics to understand program execution logic/control flow. Along with professor I also taught students in the usage of a debugger (GDB/LLVM), and a fuzzer (AFL++). Our expectation was that students would require usage of the debugger and or fuzzer to efficiently uncover the vulnerabilities.

### Disclaimer

To my knowledge this project or some close derivative is still being used for teaching. After careful consideration, and out of fairness to current, former, and future students I will not be making details of the vulnerabilities, attacks or mitigations public.<br>

In the case that you are not a current or propsective student, and would like to understand what the vulnerabilites were, how to find them, or how to mitigate them, reach out to me (contact below), and I would be more then happy to make some time on my calendar and we could go over these details and more in some detail.

---

## Contact

Contact me anytime! Day or night. My email is jackrtschetter@gmail.com, and phone number is 612-380-1832. Texting with a short introduction is the most efficient way to get a hold of me. I will respond ASAP.<br>

I would be happy to discuss in (much) greater technical detail the C programming language, and the low level analysis of binary code.<br>

I would also be happy to instruct in the various code auditing, debugging, and fuzzing techniques in which I guided my students to efficiently uncover and attack the vulnerabilities.

---

## Acknowledgements

I developed and taught from this lab during my time as an undergraduate Teaching Assistant (TA) for the class Designing and Developing Secure Software at UMN Twin Cities. At that time I was the youngest person ever in the history of the University of Minnesota to teach this class. All the previous TA's were grad students. Professor Stephen McCamant was so much more then my boss/teacher. He was also my friend, life coach, research partner and mentor.<br>

To this day Stephen McCamant was the single smartest human being that I have ever had the privilege of working and learning with. He spent hours patiently guiding me, and answering all of my questions. To my own shame Professor Stephen quickly found and corrected several mistakes I had made. In doing this he was quick to disabuse me of any hubris I might have had about my own abilities. Nevertheless I would not be one quarter of the computer scientist I am today without Professor Stephen.
