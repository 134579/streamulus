cmake_minimum_required(VERSION 3.30)
project(streamulus)

find_package(Boost CONFIG)

if (NOT Boost_FOUND)
    message(FATAL_ERROR "Could not find boost!")
endif ()
set(WARNING_FLAGS -Wall -Wextra -Wpedantic -Werror)
include_directories(${Boost_INCLUDE_DIRS})
include_directories("src/")

add_definitions(-DUSE_MAIN)

add_subdirectory(examples)

ENABLE_TESTING()
add_subdirectory(boost_test)
