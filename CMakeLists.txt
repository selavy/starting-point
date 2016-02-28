cmake_minimum_required(VERSION 2.8.11)
# TODO: set project name
project(project-name C CXX)

# set path to look for cmake modules (for find_package())
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/CMakeModules)

# set build type
set(CMAKE_BUILD_TYPE Debug)

# set folders for binaries
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)

# if you need threads: (and uncomment target_link_libraries() line in src/CMakeLists.txt)
# pthreads
#find_package(Threads REQUIRED)

# Boost
set(BOOST_ROOT $ENV{BOOST_DIR})
#set(Boost_USE_STATIC_LIBS OFF)
#set(Boost_USE_MULTITHREADED ON)
#set(Boost_USE_STATIC_RUNTIME OFF)
#add_definitions(-DBOOST_LOG_DYN_LINK)
#find_package(Boost 1.55.0 REQUIRED COMPONENTS log log_setup filesystem thread date_time program_options system)
find_package(Boost 1.55.0 REQUIRED COMPONENTS program_options)
include_directories(${Boost_INCLUDE_DIRS})

# CppUnit
find_package(CppUnit REQUIRED)
include_directories(${CPPUNIT_INCLUDE_DIR})

# compiler flags
add_compile_options("--std=c++11")
add_compile_options("-Wall")
add_compile_options("-Werror")

add_subdirectory(src)
add_subdirectory(tst)
