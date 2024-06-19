cmake_minimum_required(VERSION 3.0)

# build the test
file(GLOB test_sources *.test.cpp)

if(BUILD_TESTS)
    add_executable(util_tests ${test_sources})
    target_link_libraries(util_tests peval gtest gtest_main)

    add_test(TestUtil ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/util_tests)
endif()

add_library(pokerstove_util INTERFACE)



