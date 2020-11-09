project(step4)

add_definitions(-D_AFXDLL)
add_definitions(-DNO_WARN_MBCS_MFC_DEPRECATION)
set(CMAKE_MFC_FLAG 1)

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

add_executable(${PROJECT_NAME} WIN32 ${SRC} ${QTWINMIGRATE_FILES})
target_link_libraries(${PROJECT_NAME} Qt5::Core Qt5::Widgets Qt5::Gui)
