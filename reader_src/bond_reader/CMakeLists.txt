PROJECT(liggghts_bondreader)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
FIND_PACKAGE(ParaView REQUIRED)
INCLUDE(${PARAVIEW_USE_FILE})
IF(${PARAVIEW_VERSION_FULL} VERSION_GREATER "4.0.1")
    MESSAGE(STATUS "liggghts_bondreader > 4.0.1")
    ADD_PARAVIEW_PLUGIN(liggghts_bondreader  ${PARAVIEW_VERSION_FULL}
        SERVER_MANAGER_XML liggghts_bondreader.xml
        SERVER_MANAGER_SOURCES liggghts_bondreader.cxx
        REQUIRED_ON_SERVER)
ELSE()        
    MESSAGE(STATUS "liggghts_bondreader > 4.0.1")
    ADD_PARAVIEW_PLUGIN(liggghts_bondreader  ${PARAVIEW_VERSION_FULL}
        SERVER_MANAGER_XML liggghts_bondreader.xml
        SERVER_MANAGER_SOURCES liggghts_bondreader.cxx
        GUI_RESOURCE_FILES liggghts_bondreaderGUI.xml)
ENDIF() 
