cmake_minimum_required(VERSION 3.16)

if(CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
    project(can_common CXX)
endif()

add_library(can_common STATIC
    "${CMAKE_CURRENT_SOURCE_DIR}/src/can_common.cpp"
)
target_include_directories(can_common PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/src")
