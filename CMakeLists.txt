################################################################################
# user build settings

#ROS USAGE
SET(USE_ROS True) # Set False if you want to build this package without Catkin

################################################################################


cmake_minimum_required(VERSION 2.8.3)

set(PROJECT_NAME pugixml)
project(${PROJECT_NAME})


### Use version 2011 of C++ (c++11). By default ROS uses c++98
#see: http://stackoverflow.com/questions/10851247/how-to-activate-c-11-in-cmake
#see: http://stackoverflow.com/questions/10984442/how-to-detect-c11-support-of-a-compiler-with-cmake
#add_definitions(-std=c++11)
# add_definitions(-std=c++0x)
add_definitions(-std=c++03)


# Set the build type.  Options are:
#  Coverage       : w/ debug symbols, w/o optimization, w/ code-coverage
#  Debug          : w/ debug symbols, w/o optimization
#  Release        : w/o debug symbols, w/ optimization
#  RelWithDebInfo : w/ debug symbols, w/ optimization
#  MinSizeRel     : w/o debug symbols, w/ optimization, stripped binaries



if(NOT USE_ROS)
	set(LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_BINARY_DIR}/lib)
	set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_BINARY_DIR}/bin)
endif(NOT USE_ROS)


	
set(PUGIXML_LIBRARY_SOURCE_DIR
	${CMAKE_CURRENT_SOURCE_DIR}/src/sources
)

set(PUGIXML_LIBRARY_SOURCE_FILES
	${PUGIXML_LIBRARY_SOURCE_DIR}/pugixml.cpp
)
	
set(PUGIXML_LIBRARY_HEADER_DIR
	${CMAKE_CURRENT_SOURCE_DIR}/src/include
)

set(PUGIXML_LIBRARY_HEADER_FILES
	${PUGIXML_LIBRARY_HEADER_DIR}/pugixml/pugiconfig.hpp
	${PUGIXML_LIBRARY_HEADER_DIR}/pugixml/pugixml.hpp
)


if(USE_ROS)
  find_package(catkin REQUIRED)

  catkin_package(
      INCLUDE_DIRS ${PUGIXML_LIBRARY_HEADER_DIR}
      LIBRARIES ${PROJECT_NAME}
    )
endif()


include_directories(${PUGIXML_LIBRARY_HEADER_DIR} ${PUGIXML_LIBRARY_HEADER_DIR}/pugixml)

if(USE_ROS)
  include_directories(${catkin_INCLUDE_DIRS})
endif()


add_library(${PROJECT_NAME} ${PUGIXML_LIBRARY_SOURCE_FILES} ${PUGIXML_LIBRARY_HEADER_FILES})

if(USE_ROS)
  add_dependencies(${PROJECT_NAME} ${catkin_EXPORTED_TARGETS})
  target_link_libraries(${PROJECT_NAME} ${catkin_LIBRARIES})
endif()




################################################################################
# Create the pugixmlConfig.cmake file for other cmake projects.
IF(NOT USE_ROS)

    SET(pugixml_LIBRARY_DIR ${LIBRARY_OUTPUT_PATH} )
    #Library with the full path
    SET(pugixml_LIBRARY "${LIBRARY_OUTPUT_PATH}/lib${PROJECT_NAME}.a" )

    SET(pugixml_INCLUDE_DIR
      ${PUGIXML_LIBRARY_HEADER_DIR}
    )

    CONFIGURE_FILE( ${CMAKE_CURRENT_SOURCE_DIR}/cmake/${PROJECT_NAME}Config.cmake.in
        ${CMAKE_CURRENT_BINARY_DIR}/cmake/${PROJECT_NAME}Config.cmake @ONLY IMMEDIATE )
    export( PACKAGE ${PROJECT_NAME} )

#TODO
#    INSTALL(DIRECTORY include/pugixml DESTINATION ${CMAKE_INSTALL_PREFIX}/include FILES_MATCHING PATTERN "*.h" )
#    INSTALL(TARGETS ${PROJECT_NAME} DESTINATION ${CMAKE_INSTALL_PREFIX}/lib )
ENDIF()
