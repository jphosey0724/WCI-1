cmake_minimum_required(VERSION 3.26)
project(WCI VERSION 1.0.0)

set(CMAKE_C_STANDARD 90)
set(CMAKE_C_STANDARD_REQUIRED On)
set(CMAKE_C_EXTENSIONS Off)

set( CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/out CACHE STRING "" )

add_subdirectory(chap1)
add_subdirectory(chap2)
add_subdirectory(chap3)
add_subdirectory(chap4)
add_subdirectory(chap5)
add_subdirectory(chap6)
