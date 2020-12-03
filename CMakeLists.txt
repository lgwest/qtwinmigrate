cmake_minimum_required(VERSION 3.14)

project(qtwinmigrate)

option(BUILD_MFC_EXAMPLES "Build MFC to Qt porting examples" OFF)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)
find_package(Qt5 COMPONENTS Core Widgets Gui REQUIRED)

include_directories(${Qt5Gui_PRIVATE_INCLUDE_DIRS} ${PROJECT_SOURCE_DIR}/src)

add_library(${PROJECT_NAME} STATIC
src/QMfcApp
src/qmfcapp.cpp
src/qmfcapp.h
src/QWinHost
src/qwinhost.cpp
src/qwinhost.h
src/QWinWidget
src/qwinwidget.cpp
src/qwinwidget.h
)
add_library(${PROJECT_NAME}::${PROJECT_NAME} ALIAS ${PROJECT_NAME})
target_link_libraries(${PROJECT_NAME} Qt5::Core Qt5::Widgets Qt5::Gui)
target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/src)

if (${BUILD_MFC_EXAMPLES})
	message("--> Build MFC to Qt porting examples")
	add_subdirectory(examples/mfc)
endif()
