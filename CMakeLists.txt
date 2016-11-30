cmake_minimum_required(VERSION 3.6)
project(bitcoin_private)

set(CMAKE_CXX_STANDARD 11)

set(SOURCE_FILES main.cpp)
add_executable(bitcoin_private ${SOURCE_FILES})