cmake_minimum_required(VERSION 3.10.0)
project(cpp-training VERSION 0.1.0 LANGUAGES C CXX)

# Use a modern C++ standard (C++23). This will prefer a compiler that supports it
# and make the project portable across platforms.
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(main src/main.cpp)

include(CTest)
enable_testing()

include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        v1.17.0
)
# For Windows: Prevent overriding the parent project's compiler/linker settings
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

# Now simply link against gtest or gtest_main as needed. Eg
# add_executable(test_main tests/test_main.cpp)
# target_link_libraries(test_main gtest_main)
# add_test(NAME test_main COMMAND test_main)
