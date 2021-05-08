# How to configure the environment on Linux Ubuntu

1. Install Git, g++, make
    * `sudo apt update`
    * `sudo apt install git`
    * `sudo apt install build-essential`
    * `sudo apt-get install manpages-dev`

2. Check if the programs have been installed. Message `command not found` means an error in the installation.
    * `git --version`
    * `g++ --version`
    * `make --version`

3. Install Visual Studio Code
    * `sudo apt update`
    * `sudo apt install software-properties-common apt-transport-https wget`
    * `wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -`
    * `sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"`
    * `sudo apt update`
    * `sudo apt install code`

4. Run the VSC and install extensions
    * C/C++
    * C++ Intellisense
    * CMake
    * CMake Tools

5. Install CMake:
    `sudo apt-get install cmake`

    or a more difficult approach when the above does not work, i.e. installation from the archive:

    ```bash
    wget https://github.com/Kitware/CMake/releases/download/v3.15.2/cmake-3.15.2.tar.gz
    tar -zxvf cmake-3.15.2.tar.gz
    cd cmake-3.15.2
    ./bootstrap
    make
    sudo make install
    ```

6. Check if CMake has been installed: `cmake --version`

7. Building code

    * Create a task1.cpp file

    ```cpp
    #include<iostream>
    #include<string>

    int main() {
      std::cout << "Enter your name: ";
      std::string name;
      std::cin >> name;
      std::cout << "\nHello world! " << name << "\n";

      return 0;
    }
    ```

    * enter `g++ -std=c++17 task1.cpp -o task1`
    * Run `./task1`

8. Building code using CMake

    * Create a CMakeLists.txt file in the same directory as task1.cpp and put this inside

    ```cmake
    cmake_minimum_required(VERSION 3.10)

    # Possible, that you don't need this 2 lines.
    set(CMAKE_C_COMPILER "/usr/bin/gcc")
    set(CMAKE_CXX_COMPILER "/usr/bin/g++")

    # set the project name
    project(Tutorial)

    # add the executable
    add_executable(Tutorial task1.cpp)
    ```

    * Create build directory `mkdir build`
    * Go to the catalog `cd build`
    * Run CMake `cmake ..`
    * Build a file `make`
    * Launch the program `./Tutorial`
