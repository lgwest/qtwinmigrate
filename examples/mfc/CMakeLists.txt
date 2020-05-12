cmake_minimum_required(VERSION 3.12.0)

project(mfc2qt)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt5 COMPONENTS Core Widgets REQUIRED)

add_subdirectory(step1)
