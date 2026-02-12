## How to run C++ on your computer

You need a compiler to run C++ programs.
 We will use the terminal and simple tools.

------

### MAC

#### Step 1 — Install compiler

Open **Terminal** and run:

```
xcode-select --install
```

This installs the C++ compiler (`clang++`).

------

#### Step 2 — Create file

Create a file:

```
lab.cpp
```

You can use:

- VS Code
- TextEdit (set to plain text)
- Nano in terminal

Example in terminal:

```
nano lab.cpp
```

Paste your code and save.

------

#### Step 3 — Compile

```
clang++ lab.cpp -o lab
```

This creates an executable file called `lab`.

------

#### Step 4 — Run

```
./lab
```

------

#### If you get “iostream not found” error

Install build tools:

```
brew install gcc
```

Then compile with:

```
g++ lab.cpp -o lab
./lab
```

------

### WINDOWS

We use VS Code and MinGW.

#### Step 1 — Install VS Code

Download and install:
 https://code.visualstudio.com

------

#### Step 2 — Install compiler

Download MinGW: https://www.mingw-w64.org

Install with:

- Architecture: x86_64
- Threads: POSIX
- Exception: SEH

Add MinGW to your PATH.

Test in terminal:

```
g++ --version
```

------

#### Step 3 — Compile

Open terminal in VS Code and run:

```
g++ lab.cpp -o lab.exe
```

------

#### Step 4 — Run

```
lab.exe
```

------

### LINUX

#### Step 1 — Install compiler

```
sudo apt update
sudo apt install g++
```

------

#### Step 2 — Compile

```
g++ lab.cpp -o lab
```

------

#### Step 3 — Run

```
./lab
```

------

### Test Program

Students should test this first:

```
#include <iostream>

int main() {
    std::cout << "C++ is working!";
    return 0;
}
```

If this runs, your setup works.

------

### Optional

If you want to run C++ on a tablet or mobile phone, use an online compiler: https://www.onlinegdb.com

Paste code and run. No installation needed.