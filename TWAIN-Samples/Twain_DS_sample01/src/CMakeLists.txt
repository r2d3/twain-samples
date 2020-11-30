cmake_minimum_required(VERSION 3.18)
project(TWAINDS)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt5 COMPONENTS Core Gui Widgets REQUIRED)

add_library(TWAINDS SHARED
    ../../common/CTiffWriter.cpp
    ../../common/CommonTWAIN.cpp
    CommonDS.cpp
    CScanner_FreeImage.cpp
    CTWAINDS_Base.cpp
    CTWAINDS_FreeImage.cpp
    DSMInterface.cpp
    TWAINContainer.cpp
    TWAINContainerFix32.cpp
    TWAINContainerFrame.cpp
    TWAINContainerInt.cpp
    CTWAINDS_Sample1.cpp
    TWAIN_UI.cpp
    TWAINContainerString.cpp
    TWAINContainerFix32Range.cpp
    TWAINContainerBool.cpp
    QT_UI.cpp
    Qt_MainForm.cpp
    Qt_About.cpp
    Qt_ProfileName.cpp

    ../../common/Common.h
    ../../common/CommonTWAIN.h
    ../../common/CTiffWriter.h
    CScanner_FreeImage.h
    CTWAINDS_Base.h
    CTWAINDS_FreeImage.h
    CommonDS.h
    DSMInterface.h
    TWAINContainerFix32.h
    TWAINContainerFrame.h
    TWAINContainer.h
    TWAINContainerInt.h
    CTWAINDS_Sample1.h
    TWAIN_UI.h
    TWAINContainerString.h
    TWAINContainerFix32Range.h
    TWAINContainerBool.h
    QT_UI.h
    Qt_MainForm.h
    Qt_About.h
    Qt_ProfileName.h

    About.ui
    MainForm.ui
    ProfileName.ui

    TWAINDS.def
)

target_include_directories(TWAINDS PRIVATE
    ../../common
    ../../pub/external/include
    ../visual_studio/
    )

target_link_libraries( TWAINDS
  Qt5::Core
  Qt5::Gui
  Qt5::Widgets
  ../../pub/external/lib/win64/FreeImage
  )


