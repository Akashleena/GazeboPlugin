#set(MODULE_NAME "GazeboPlugin")
cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

find_package(gazebo REQUIRED)
include_directories(${GAZEBO_INCLUDE_DIRS})
link_directories(${GAZEBO_LIBRARY_DIRS})

add_library(GazeboPlugin SHARED ./src/GazeboPlugin.cpp) #add_library(${PROJECT_NAME} ${${PROJECT_NAME}_SRCS})
target_link_libraries(GazeboPlugin ${GAZEBO_LIBRARIES})
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}")
