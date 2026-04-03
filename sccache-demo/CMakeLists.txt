cmake_minimum_required(VERSION 3.16)
project(hello C)

find_program(SCCACHE sccache)
if(SCCACHE)
    set(CMAKE_C_COMPILER_LAUNCHER ${SCCACHE})
    message(STATUS "Using sccache: ${SCCACHE}")
else()
    message(WARNING "sccache not found, building without compiler cache")
endif()

add_executable(hello main.c)
