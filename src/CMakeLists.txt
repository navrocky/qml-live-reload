cmake_minimum_required(VERSION 3.1)
set(TARGET qmllivereload)
project(${TARGET} CXX)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

find_package(Qt5Core)
find_package(Qt5Quick)

set(CMAKE_AUTOMOC ON)
#set(CMAKE_AUTOUIC ON)
#set(CMAKE_AUTORCC ON)

set(SOURCES
    qmllivereload.h
    qmllivereload.cpp
    sourcefileswatcher.h
    sourcefileswatcher.cpp
    localfileswatcher.h
    localfileswatcher.cpp
    recursivedirwatcher.h
    recursivedirwatcher.cpp
)

add_library(${TARGET} STATIC ${SOURCES})

target_link_libraries(${TARGET}
    Qt5::Core
    Qt5::Quick
)
