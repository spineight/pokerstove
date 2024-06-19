cmake_minimum_required(VERSION 3.0)

project(pokerstove)


option(BUILD_TESTS OFF)
if(BUILD_TESTS)
    # Set up gtest. This must be set up before any subdirectories are
    # added which will use gtest.
    add_subdirectory(src/ext/googletest)
    include_directories(${GTEST_INCLUDE_DIRS})
    link_directories(${GTEST_LIBS_DIR})
    add_definitions("-fPIC")
    enable_testing()
endif()

include_directories(${Boost_INCLUDE_DIR})
link_directories(${Boost_LIBRARY_DIRS})


# Also search for includes in PROJECT_BINARY_DIR to find config.h.
include_directories("${PROJECT_BINARY_DIR}")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)

# This controls whether or not to build the python bridge
if(BUILD_PYTHON)
    add_subdirectory(src/lib/python)
endif()

# add the actual code
# include_directories(src/lib)
add_subdirectory(src/lib)
# add_subdirectory(src/programs)

# Add make install functionality
# install(TARGETS peval)
# install(TARGETS penum)
# install(TARGETS ps-colex)
# install(TARGETS ps-eval)
# install(TARGETS ps-lut)
