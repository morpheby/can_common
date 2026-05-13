cmake_minimum_required(VERSION 3.16)

if(DEFINED ESP_PLATFORM)
    idf_component_register(
        SRCS
            "${CMAKE_CURRENT_SOURCE_DIR}/src/can_common.cpp"
        INCLUDE_DIRS
            "${CMAKE_CURRENT_SOURCE_DIR}/src"
        REQUIRES
            arduino-esp32
    )
else()
    if(CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
        project(can_common CXX)
    endif()
    
    add_library(can_common STATIC
        "${CMAKE_CURRENT_SOURCE_DIR}/src/can_common.cpp"
    )
    target_include_directories(can_common PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/src")
endif()
