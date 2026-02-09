cmake_minimum_required(VERSION 3.3)
project(streamulus)

find_package(Boost 1.58.0)

if(NOT Boost_FOUND)
    message(FATAL_ERROR "Could not find boost!")
endif()

include_directories(${Boost_INCLUDE_DIRS})
include_directories("src/")

add_definitions(-DUSE_MAIN)

add_subdirectory(examples)

ENABLE_TESTING()
add_subdirectory(boost_test)
