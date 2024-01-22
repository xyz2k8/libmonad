cmake_minimum_required(VERSION 3.0)

project(monad VERSION 1.0)
set(TESTNAME t_monad)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

aux_source_directory(Tests TEST)
add_executable(${TESTNAME} ${TEST})

set(GTEST gtest/googletest-1.14.0/googletest)

set(INCLUDES lib)
target_include_directories(${TESTNAME} PRIVATE ${INCLUDES} ${GTEST}/include/gtest)


link_directories(${GTEST}/build/lib)
target_link_libraries(${TESTNAME} gtest gtest_main pthread)



