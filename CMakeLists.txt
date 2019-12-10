cmake_minimum_required(VERSION 3.10)

project(rtsp)

set(CMAKE_CXX_FLAGS -g)

file(GLOB RTSP_SOURCES ${CMAKE_SOURCE_DIR}/net/*.cpp ${CMAKE_SOURCE_DIR}/xop/*.cpp )

file(GLOB SOURCES ${CMAKE_SOURCE_DIR}/*.cpp )

include_directories(${CMAKE_SOURCE_DIR})

add_library(net ${RTSP_SOURCES})

add_executable(rtsp ${SOURCES})

target_link_libraries(rtsp avcodec avfilter avutil net pthread)
