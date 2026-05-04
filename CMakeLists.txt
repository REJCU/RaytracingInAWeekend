cmake_minimum_required(VERSION 3.10)

# 1. Project metadata
project(RayTracingOneWeekend LANGUAGES CXX)

# 2. Require C++11 (the book's baseline)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# 3. Add compiler optimizations (Optional but recommended for Ray Tracing)
if(MSVC)
    add_compile_options(/W4 /O2) # High warning level and Speed optimization for Windows
else()
    add_compile_options(-Wall -Wextra -O3) # High warning and Aggressive optimization for Linux/Mac
endif()

# 4. Create the executable
add_executable(in_one_weekend main.cpp)
