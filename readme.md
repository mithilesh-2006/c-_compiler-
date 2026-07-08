# C++ Compiler Setup for Visual Studio Code

This repository contains a pre-configured Visual Studio Code task setup for compiling and running C++ programs using **g++ (C++17)** with **input redirection** (`input.txt`) and **output redirection** (`output.txt`).

---

## Repository Structure

```
.
├── .vscode
│   └── tasks.json
├── input.txt
├── output.txt
└── README.md
```

---

# Prerequisites

Before using this repository, make sure the following software is installed.

### 1. Install Visual Studio Code

Download and install VS Code from:

https://code.visualstudio.com/

---

### 2. Install MinGW-w64 (g++ Compiler)

Download and install MinGW-w64.

After installation, verify that `g++` is available by opening Command Prompt and running:

```bash
g++ --version
```

If the version is displayed, the compiler is installed correctly.

Example:

```
g++.exe (Rev5, Built by MSYS2 project) 16.1.0
```

---

### 3. Install the VS Code C/C++ Extension

Open VS Code.

Go to **Extensions (Ctrl + Shift + X)**

Search for:

```
C/C++
```

Install the extension published by Microsoft.

---

# Add g++ to PATH

If `g++ --version` does not work, add the compiler's **bin** folder to the system PATH.

Example:

```
C:\msys64\ucrt64\bin
```

Restart VS Code after updating the PATH.

---

# Clone the Repository

```bash
git clone <repository-url>
```

Open the project folder in Visual Studio Code.

---

# Repository Files

## `.vscode/tasks.json`

This file contains two tasks.

### 1. Compile

Compiles the currently opened C++ file.

Command used:

```bash
g++ -std=c++17 filename.cpp -o filename.exe
```

---

### 2. Compile and Run

This task:

- Compiles the current file
- Reads input from `input.txt`
- Writes output to `output.txt`
- Displays the output in the terminal

Command executed:

```bash
g++ -std=c++17 filename.cpp -o filename.exe

filename.exe < input.txt > output.txt

type output.txt
```

---

# How to Use

## Step 1

Open your C++ source file.

Example:

```
main.cpp
```

---

## Step 2

Write your program.

Example:

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a, b;
    cin >> a >> b;

    cout << a + b;

    return 0;
}
```

---

## Step 3

Provide the input inside `input.txt`.

Example:

```
10 20
```

---

## Step 4

Press

```
Ctrl + Shift + B
```

VS Code will automatically execute the default task:

```
Compile and Run
```

---

## Step 5

The program will

- Compile successfully
- Read input from `input.txt`
- Save the output to `output.txt`
- Display the contents of `output.txt` in the terminal

Example:

```
30
```

---

# Running Only the Compiler

If you only want to compile the program without executing it:

1. Press

```
Ctrl + Shift + P
```

2. Select

```
Tasks: Run Task
```

3. Choose

```
compile
```

This creates the executable file without running it.

---

# Input and Output Files

## input.txt

Store all program inputs here.

Example:

```
5
10
```

---

## output.txt

After execution, the program output will be written here automatically.

Example:

```
15
```

---

# Notes

- The tasks compile using the **C++17** standard.
- The currently opened `.cpp` file is compiled.
- Every source file generates its own executable.
- The executable is created in the same directory as the source file.
- The program uses file redirection for input and output.
- Ensure that `input.txt` exists before running programs that require input.

---

# Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + Shift + B` | Compile and Run |
| `Ctrl + Shift + P` | Open Command Palette |
| `Tasks: Run Task` | Select a specific task |

---

# Troubleshooting

### 'g++' is not recognized

- Verify that MinGW/MSYS2 is installed.
- Ensure the compiler's `bin` directory is added to the system PATH.
- Restart VS Code after updating the PATH.

---

### Program waits for input

Make sure `input.txt` exists and contains the required input values.

---

### No output generated

Check for compilation errors in the terminal. If compilation succeeds, verify that the program writes output to `stdout` and that `output.txt` is being created correctly.

---

# License

This repository is provided for educational purposes and can be modified as needed.