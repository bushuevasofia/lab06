cmake_minimum_required(VERSION 3.11)
project(solver_lib LANGUAGES CXX)

if(NOT TARGET solver_lib)
    add_library(solver_lib STATIC solver.cpp)
    target_include_directories(solver_lib PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    )
endif()
