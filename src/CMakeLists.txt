# src/CMakeLists.txt

include_directories("${CMAKE_SOURCE_DIR}/include")

# TODO: add library
# TODO: use new library name to link in tst/CMakeLists.txt
# add_library(library-name
#         files.cpp
#         )

add_executable(
        driver
        main.cpp
        command_line.cpp
        )
        
# link driver program with library code
# target_link_libraries(driver library-name)

target_link_libraries(driver ${Boost_LIBRARIES})
# if you need threads:
#target_link_libraries(driver ${CMAKE_THREAD_LIBS_INIT})
