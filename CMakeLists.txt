cmake_minimum_required(VERSION 2.8)

set(TARGET darknet)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wno-unused-result -Wno-unknown-pragmas -Wfatal-errors -Ofast -fPIC")

file(GLOB DARKNET_SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)
list(REMOVE_ITEM DARKNET_SOURCES 
  ${CMAKE_CURRENT_SOURCE_DIR}/src/compare.c
)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

add_library(${TARGET} STATIC ${DARKNET_SOURCES})