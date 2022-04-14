cmake_minimum_required(VERSION 3.1)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(solver)

add_executable(solver equation.cpp)

include_directories(../solver_lib ../formatter_ex_lib)

add_subdirectory(../solver_lib solver_lib)
add_subdirectory(../formatter_ex_lib formatter_ex)

target_link_libraries(solver solver_lib formatter_ex)

install(TARGETS solver RUNTIME DESTINATION solver_bin_output)
set(CPACK_SOURCE_GENERATOR "TGZ;ZIP")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "maintainer")
set(MACOSX_BUNDLE TRUE)

include(CPack)
