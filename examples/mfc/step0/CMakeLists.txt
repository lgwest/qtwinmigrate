project(step0)


add_definitions(-DWINVER=0x0601)
add_definitions(-D_AFXDLL)
add_definitions(-D_CRT_SECURE_NO_WARNINGS)
add_definitions(-DNO_WARN_MBCS_MFC_DEPRECATION)
set(CMAKE_MFC_FLAG 2)


set(SRC
childview.cpp
childview.h
mainframe.cpp
mainframe.h
qtmfc.rc
res/QtMfc.ico
res/QtMfc.rc2
Resource.h
StdAfx.cpp
StdAfx.h
)
add_executable(${PROJECT_NAME} WIN32 ${SRC})
target_link_libraries(${PROJECT_NAME})
