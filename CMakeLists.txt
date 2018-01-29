cmake_minimum_required(VERSION 2.8.4)
project(mytest)

#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

add_custom_target(mytest COMMAND make -C ${mytest_SOURCE_DIR}
        CLION_EXE_DIR=${PROJECT_BINARY_DIR})

#AUX_SOURCE_DIRECTORY(src SOURCE_FILES)
add_definitions(-DGPU=1 -DCUDANN=1 -DOPENCV=1)
include_directories(include)
FILE(GLOB SOURCE_FILES src/*.c src/*.cu include/* examples/*)
#set(SOURCE_FILES $(wildcard src/*.c))
add_executable(xxx ${SOURCE_FILES})
