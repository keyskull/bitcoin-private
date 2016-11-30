cmake_minimum_required(VERSION 3.6)
project(bitcoin_private)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES main.cpp)
add_executable(bitcoin_private ${SOURCE_FILES})
add_custom_target(Build-Bitcoin
        COMMAND cd ${CMAKE_SOURCE_DIR}/bitcoin/depends && make HOST=i686-w64-mingw32 -j8 && cd .. && ./autogen.sh &&
        cd ${CMAKE_SOURCE_DIR}/cmake-build-debug/build &&
        CONFIG_SITE=$PWD/depends/i686-w64-mingw32/share/config.site ${CMAKE_SOURCE_DIR}/bitcoin/configure
        )