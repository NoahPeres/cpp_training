cmake_minimum_required(VERSION 3.24.0)
project(cpp-training VERSION 0.1.0 LANGUAGES C CXX)

# Use a modern C++ standard (C++23). This will prefer a compiler that supports it
# and make the project portable across platforms.
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_COMPILE_WARNING_AS_ERROR ON)

add_executable(cpp-training src/main.cpp)
target_link_libraries(cpp-training PRIVATE "-lstdc++exp")


enable_testing()
add_subdirectory(tests)