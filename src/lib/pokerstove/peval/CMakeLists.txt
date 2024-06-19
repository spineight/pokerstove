cmake_minimum_required(VERSION 3.0)
find_package (Threads)


file(GLOB test_sources *.test.cpp)

if(BUILD_TESTS)
  # build the test 
  add_executable(peval_tests ${test_sources})
  target_link_libraries(peval_tests peval gtest gtest_main ${CMAKE_THREAD_LIBS_INIT})

  add_test(TestPeval ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/peval_tests)
endif()

# build the library sources from all sources, removing the test sources
file(GLOB lib_sources *.cpp)
foreach(source_file ${test_sources})
  list(REMOVE_ITEM lib_sources ${source_file})
endforeach()

# peval library
add_library(peval ${lib_sources})

target_link_directories(peval PUBLIC pokerstove_util)



