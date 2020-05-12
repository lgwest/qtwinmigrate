project(step5)

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

add_executable(${PROJECT_NAME} ${SRC})
target_link_libraries(${PROJECT_NAME} Qt5::Gui Qt5::Core Qt5::Widget)