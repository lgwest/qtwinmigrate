cmake_minimum_required(VERSION 3.14)

project(step5)

add_definitions(-D_WIN32_WINNT=0x0601)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

if(CMAKE_VERSION VERSION_LESS "3.7.0")
    set(CMAKE_INCLUDE_CURRENT_DIR ON)
endif()

find_package(Qt5 COMPONENTS Core Widgets Gui REQUIRED)

set(SRC
)

add_executable(step5
childview.cpp
childview.h
mainframe.cpp
mainframe.h
optionsdialog.ui
qtmfc.cpp
qtmfc.rc
res/qtmfc.bmp
res/QtMfc.ico
)
target_link_libraries(step5 Qt5::Gui Qt5::Core Qt5::Widgets)
