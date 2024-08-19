# vsc-sfml-gcc-boilerplate

This repository serves as a starting point for those who want to use SFML for a project with Visual Studio Code.

## Prerequisites

To use this boilerplate, ensure the following are installed on your machine:

* Visual Studio Code with the CMake extension installed.
* MinGW, compatible with the specific SFML library you plan to use (e.g., WinLibs MSVCRT 13.1.0 (64-bit) for SFML 2.6.1 64-bit).

## Step 1: Make MinGW Available for VSC

You can make MinGW available in Visual Studio Code by adding an entry to the `cmake-tools-kits.json` file. Follow these steps:

### Step 1.1: Open the VSC Command Palette

Press `Ctrl + Shift + P` to open the Command Palette.

### Step 1.2: Edit CMake Kits

Type in: `CMake: Edit User-Local CMake Kits`

### Step 1.3: Add the MinGW Entry

Add the following entry to the `cmake-tools-kits.json` file:

*(Note: Replace the paths with the actual paths on your machine for `gcc.exe`, `g++.exe`, and `mingw/bin`)*

```json
{
    "name": "MinGW Custom",
    "compilers": {
        "C": "C:/tools/mingw/bin/gcc.exe",
        "CXX": "C:/tools/mingw/bin/g++.exe"
    },
    "environmentVariables": {
        "PATH": "C:/tools/mingw/bin"
    },
    "preferredGenerator": {
        "name": "MinGW Makefiles"
    }
}
```
## Step 2: Set Up Your Project

1. Download the SFML library and place it in the `src` directory. (Folder Name SFML-2.6.1)
2. Add the main.cpp file from this repo for a smoke test
3. Open your project folder with Visual Studio Code
4. Press `Ctrl + Shift + P` to open the Command Palette and type `CMake: Quick Start`.
5. Enter a project name.
6. Select `C++ Project Create C++Project`
7. Select `Executable Create Executable`
8. Skip CPAck and CTest by just klicking ok without selecting anything
9. Press esc to skip the generation of a preset
10. Close and start Visual Studio Code
11. Press `Ctrl + Shift + P` to open the Command Palette and type `CMake: Quick Start`. 
12. Select the kit `MinGW-for-SFML`.
    
## Step 3: Edit CMakeLists.txt

Finally, edit the CMakeLists.txt file as described in the project files to configure the project properly.
