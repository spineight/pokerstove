add_subdirectory (pokerstove/util)

add_subdirectory (pokerstove/peval)
add_subdirectory (pokerstove/penum)


target_include_directories(peval PUBLIC ${CMAKE_CURRENT_LIST_DIR}/)
target_include_directories(pokerstove_util INTERFACE ${CMAKE_CURRENT_LIST_DIR}/)
target_include_directories(penum PUBLIC ${CMAKE_CURRENT_LIST_DIR}/)


