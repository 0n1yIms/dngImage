cmake_minimum_required(VERSION 3.6.0)
project(DngImage)

add_library(dngImage STATIC
        ${CMAKE_CURRENT_SOURCE_DIR}/dngImage.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/dngImage.h
        )
target_include_directories(dngImage PUBLIC 
        ${CMAKE_CURRENT_SOURCE_DIR}
        )
target_link_libraries(dngImage dngSdk)