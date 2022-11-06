cmake_minimum_required (VERSION 3.14)

project (voltlib VERSION 0.1.0)

set (VOLTLIB_SOURCES
    voltlib.cpp
)

set (VOLTLIB_HEADERS
    voltlib.hpp
)

list (TRANSFORM VOLTLIB_SOURCES PREPEND "src/")
list (TRANSFORM VOLTLIB_HEADERS PREPEND "include/")

add_library(${PROJECT_NAME} ${VOLTLIB_SOURCES})
set_target_properties(${PROJECT_NAME} PROPERTIES
    VERSION ${PROJECT_VERSION}
    PUBLIC_HEADER ${VOLTLIB_HEADERS})

target_include_directories(${PROJECT_NAME} PRIVATE include/)
