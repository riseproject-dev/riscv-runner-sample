cmake_minimum_required(VERSION 3.16)
project(hello C)

find_program(CCACHE NAMES sccache ccache)
if(CCACHE)
    set(CMAKE_C_COMPILER_LAUNCHER ${CCACHE})
    message(STATUS "Using compiler cache: ${CCACHE}")
else()
    message(FATAL_ERROR "sccache nor ccache not found, not building (it's a demo for ccache and sccache!)")
endif()

add_executable(hello main.c)
