# How to configure the environment on Windows 10

## IDE installation

1. [Download Visual Studio Code](https://code.visualstudio.com/download).
2. Run the VSC and go to extensions.
3. Zainstaluj C/C++, C++ Intellisense, CMake, CMake Tools.

## git-bash installation

1. [Download-git-bash](https://git-for-windows.github.io/)
2. During installation at `Select Components` screen select everything
3. In the next step, select your favorite editor (I recommend Visual Studio Code)
4. In the following steps, select:
    * Git from the command line and also from 3rd-party software
    * use the OpenSSL library
    * Checkout Window-style, commit Unix-style line endings
    * Use MinTTY
    * Enable file system caching, enable git credential manager, enable symbolic links
5. Click `install`
6. Start git-bash and configure your data in git-bash:
    * `git config --global user.name "Your Name"`
    * `git config --global user.email "your@email.com`
7. Check if the data has been set correctly:

    * `git config --global --list`

## Cygwin installation

1. [Download-Cygwin](https://cygwin.com/install.html)
2. Install
3. After installation `select packages` screen will appear, here we can choose what we want to install
    In search, enter following phrases and select the latest versions of the packages for installation:
    * search `cmake` -> Devel -> Install all 5 packages (latest versions),
    * search `g++` -> Devel -> Install all 5 packages (latest versions),
    * search `clang` -> Devel -> Install all 5 packages (latest versions).
    * search `make` -> Similarly, install all 4 packages
4. Run Cygwin
5. Enter `g++ --version` to check if it has been installed correctly
6. Enter `clang --version`
7. Enter `cmake --version`
8. Create a file with a simple code:

    ```cpp
    #include <iostream>
    #include <string>

    int main() {
      std::cout << "Enter your name: ";
      std::string name;
      std::cin >> name;
      std::cout << "\nHello world! " << name << "\n";

      return 0;
    }
    ```

9. Name it task1.cpp and then build it using the command:
    `g++ -std=c++17 task1.cpp -o task1`
10. Run the program `./task1.exe`

## Using CMake

1. Create a file `CMakeLists.txt` and put this inside it:

    ```cmake
      cmake_minimum_required(VERSION 3.10)

      set(CMAKE_C_COMPILER "/usr/bin/gcc")
      set(CMAKE_CXX_COMPILER "/usr/bin/g++")

      # set the project name
      project(Tutorial)

      # add the executable
      add_executable(Tutorial task1.cpp)
    ```

2. Create a build directory `mkdir build`
3. Go to the catalog `cd build`
4. Run CMake `cmake ..`
5. Build a program `make`
6. Run the program `./Tutorial.exe`

## Using CMake from Visual Studio Code

[This link](https://www.youtube.com/watch?v=v1ypejhdje) leads to a great short tutorial about how to write and compile Helloworld using Cmake and Visual Studio Code.
