# C++ Key Logger for Windows OS

## What does the app do?
Once the program is running, it will automatically try to hide the keyboard and print any key pressed inside a log file (*log-data.txt*)

## Programming Languages:
- C++

## Frameworks & Libraries:
- string (to work with c++ strings)
- fstream (to work with c++ file streams)
- windows.h (to hide the keyboard on Windows OS)
- algorithm (for utility functions like *std::any_of*)

## Implementation:
Explaining the file architecture will make you also understand the entire program:
- main.cpp (containing the logic)
- utils.hpp (containing the function declarations and macros)
```c++
#define current_function_name std::string("error in: ") + __FUNCTION__ + " -> "
```
- utils.cpp (containing the function definitions)
```c++
void open_file_stream(std::fstream & file_stream, const std::string & file_name,
    const std::ios_base::openmode opening_mode) {
    
    file_stream.open(file_name, opening_mode);

    if (file_stream.fail() or not file_stream) {
        throw std::runtime_error(current_function_name + "cannot open " + file_name);
    }
}
```