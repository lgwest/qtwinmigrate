project(step5)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)
find_package(Qt5 COMPONENTS Core Widgets Gui REQUIRED)

set(SRC
childview.cpp
childview.h
mainframe.cpp
mainframe.h
qtmfc.cpp
qtmfc.rc
res/qtmfc.bmp
res/QtMfc.ico
)

add_executable(${PROJECT_NAME} WIN32 ${SRC})
target_link_libraries(${PROJECT_NAME} Qt5::Gui Qt5::Core Qt5::Widget)