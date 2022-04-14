cmake_minimum_required(VERSION 3.1)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(solver)

add_executable(solver equation.cpp)

include_directories(../solver_lib ../formatter_ex_lib)

add_subdirectory(../solver_lib solver_lib)
add_subdirectory(../formatter_ex_lib formatter_ex)

target_link_libraries(solver solver_lib formatter_ex)
