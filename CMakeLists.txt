cmake_minimum_required(VERSION 3.29)
set(CMAKE_CXX_COMPILER g++-14)
project(sv VERSION 0.0.0 LANGUAGES CXX)

set(CMAKE_CXX_SCAN_FOR_MODULES OFF)
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(doctest 2.4.11 EXACT REQUIRED)
add_compile_definitions(DOCTEST_CONFIG_SUPER_FAST_ASSERTS)
link_libraries(doctest::doctest) # Header only dependency

add_subdirectory(sv)
add_executable(tests test.cpp)
target_link_libraries(tests sv)

include(CTest)
include(doctest)
doctest_discover_tests(tests)
