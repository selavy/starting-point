cmake_minimum_required(VERSION 2.8.11)
# TODO: set project name
project(project-name C CXX)

# set path to look for cmake modules (for find_package())
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/CMakeModules)

# set build type
set(CMAKE_BUILD_TYPE Debug)

# set folders for binaries
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)

# CppUnit
find_package(CppUnit REQUIRED)
include_directories(${CPPUNIT_INCLUDE_DIR})

# compiler flags
add_compile_options("--std=c++11")
add_compile_options("-Wall")
add_compile_options("-Werror")

add_subdirectory(src)
add_subdirectory(tst)
