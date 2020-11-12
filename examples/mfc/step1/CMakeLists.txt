project(step1)

add_definitions(-D_AFXDLL)
add_definitions(-DNO_WARN_MBCS_MFC_DEPRECATION)
set(CMAKE_MFC_FLAG 1)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)
find_package(Qt5 COMPONENTS Core Widgets Gui REQUIRED)

#https://gist.github.com/giucam/3b5f685330bf3ab21aa5c684072d9a12
# alternative to Qt5Gui_PRIVATE_INCLUDE_DIRS
#foreach(dir ${Qt5Widgets_INCLUDE_DIRS})
#    include_directories(${dir}/${Qt5Gui_VERSION_STRING}/QtGui/)
#endforeach(dir)

# Qt5Gui_PRIVATE_INCLUDE_DIRS needed for #include <qpa/qplatformnativeinterface.h> in qwinwidget.cpp
message("Qt5Gui_PRIVATE_INCLUDE_DIRS ${Qt5Gui_PRIVATE_INCLUDE_DIRS}")
include_directories(${Qt5Gui_PRIVATE_INCLUDE_DIRS})
include_directories(${QTWINMIGRATE_DIR})



set(SRC
childview.cpp
childview.h
mainframe.cpp
mainframe.h
qtmfc.cpp
qtmfc.h
qtmfc.rc
res/QtMfc.ico
res/QtMfc.rc2
Resource.h
StdAfx.cpp
StdAfx.h
)

#include_directories(${CMAKE_CURRENT_BINARY_DIR})
add_executable(${PROJECT_NAME} WIN32 ${SRC})
target_link_libraries(${PROJECT_NAME} Qt5::Core Qt5::Widgets)
