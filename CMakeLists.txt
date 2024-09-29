cmake_minimum_required(VERSION 3.11)

project(pdf CXX)
set(CMAKE_CXX_STANDARD 17)

include(${CMAKE_BINARY_DIR}/conanbuildinfo_multi.cmake)
conan_basic_setup(TARGETS)

add_executable(pdf main.cpp)

target_include_directories(pdf PRIVATE CONAN_PKG::pdf-writer)
target_link_libraries(pdf CONAN_PKG::pdf-writer)
