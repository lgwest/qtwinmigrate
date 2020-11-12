cmake_minimum_required(VERSION 3.14.0)


project(mfc2qt LANGUAGES CXX)

add_definitions(-D_WIN32_WINNT=0x0601)

set(QTWINMIGRATE_DIR ${PROJECT_SOURCE_DIR}/../../src)

set(QTWINMIGRATE_FILES
${QTWINMIGRATE_DIR}/qwinwidget.cpp
${QTWINMIGRATE_DIR}/qwinwidget.h
${QTWINMIGRATE_DIR}/qwinhost.cpp
${QTWINMIGRATE_DIR}/qwinhost.h
${QTWINMIGRATE_DIR}/qmfcapp.cpp
${QTWINMIGRATE_DIR}/qmfcapp.h
)


add_subdirectory(step1)
add_subdirectory(step2)
add_subdirectory(step3)
add_subdirectory(step4)
add_subdirectory(step5)

