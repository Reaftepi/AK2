cmake_minimum_required(VERSION 3.10)
project(Pavlenko_clean)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_library(calculator SHARED calculator.cpp
        calculator.cpp
        calculator.h)
target_include_directories(calculator PUBLIC ${CMAKE_SOURCE_DIR})

add_executable(Pavlenko main.cpp)
target_link_libraries(Pavlenko PRIVATE calculator)

