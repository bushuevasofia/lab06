cmake_minimum_required(VERSION 3.5)
project(formatter_ex LANGUAGES CXX)

if(NOT TARGET formatter)
    add_subdirectory(${CMAKE_SOURCE_DIR}/formatter_lib ${CMAKE_CURRENT_BINARY_DIR}/formatter_lib)
endif()

if(NOT TARGET formatter_ex)
    add_library(formatter_ex STATIC formatter_ex.cpp)
    target_include_directories(formatter_ex PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    )
    target_link_libraries(formatter_ex PUBLIC formatter)
endif()
