cmake_minimum_required(VERSION 3.16)
project(qt-wordcount LANGUAGES CXX)

set(CMAKE_AUTOMOC ON)

find_package(Qt5 REQUIRED COMPONENTS Concurrent Core Widgets)

add_executable("${PROJECT_NAME}" main.cpp)

target_link_libraries("${PROJECT_NAME}" PRIVATE
    Qt5::Concurrent
    Qt5::Core
    Qt5::Widgets
)

