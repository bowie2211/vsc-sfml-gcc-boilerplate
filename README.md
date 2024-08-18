# vsc-sfml-gcc-boilerplate

This repo is a starting point for people who want to use sfml for a project, using 
visual studio code.

It works for following prerequisites:

* Visual Studio Code installed with CMake Extension installed
* MinGW that is required for the respective SFML lib (e.g. WinLibs MSVCRT 13.1.0 (64-bit) for SFML 2.6.1 64 Bit) is on the local machine


Step 1:
Make the mingw available for vsc 
I have done this by adding an entry in cmake-tools-kits.json file with the following steos:

Step 1.1: Open the VSC Command Palette: Ctrl + Shift + P 
Step 1.2: Type in: CMake: Edit User-Local CMake Kits
Step 1.3: Add the following entry to cmake-tools-kits.json

(Remark: Put your path to 
gcc.exe for "C" 
g++.exe for "C++"
and
mingw/bin for PATH)
----

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

----

Then Open the command palette and type in Quick start
Give a project name 
Select the Kit mingw-for sfml
Download the SFML Library
Add it below src

Edit the CMakeLists.txt as described in the file in that project
