cmake_minimum_required(VERSION 3.24)
project(wren)

file(GLOB_RECURSE WREN_SRC "src/*.c")
file(GLOB_RECURSE WREN_HEADER "src/*.h")

set(WREN_SRC ${WREN_SRC} ${WREN_HEADER})

add_library(wren STATIC ${WREN_SRC})

target_include_directories(
    wren
    PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}/src/include"
)

target_include_directories(
    wren
    PRIVATE
    "${CMAKE_CURRENT_SOURCE_DIR}/src/optional"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/vm"
)
