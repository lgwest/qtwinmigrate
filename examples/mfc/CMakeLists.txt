cmake_minimum_required(VERSION 3.14.0)


project(mfc2qt LANGUAGES CXX)

add_definitions(-D_WIN32_WINNT=0x0601)

set(QTWINMIGRATE_DIR ${PROJECT_SOURCE_DIR}/../../src)
include_directories(${QTWINMIGRATE_DIR})

set(QTWINMIGRATE_FILES
${QTWINMIGRATE_DIR}/qwinwidget.cpp
${QTWINMIGRATE_DIR}/qwinwidget.h
${QTWINMIGRATE_DIR}/qwinhost.cpp
${QTWINMIGRATE_DIR}/qwinhost.h
${QTWINMIGRATE_DIR}/qmfcapp.cpp
${QTWINMIGRATE_DIR}/qmfcapp.h
)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)
find_package(Qt5 COMPONENTS Core Widgets Gui REQUIRED)

include_directories(Qt5Gui_PRIVATE_INCLUDE_DIRS )
#include_directories(${CMAKE_CURRENT_BINARY_DIR})

#https://gist.github.com/giucam/3b5f685330bf3ab21aa5c684072d9a12
#foreach(dir ${Qt5Widgets_INCLUDE_DIRS})
#    include_directories(${dir}/${Qt5Gui_VERSION_STRING}/QtGui/)
#endforeach(dir)
#include_directories(${Qt5Gui_PRIVATE_INCLUDE_DIRS})

add_subdirectory(step1)
add_subdirectory(step2)
add_subdirectory(step3)
add_subdirectory(step4)
#add_subdirectory(step5)

