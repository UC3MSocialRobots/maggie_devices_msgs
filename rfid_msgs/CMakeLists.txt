cmake_minimum_required(VERSION 2.8.3)
project(rfid_msgs)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS std_msgs message_generation)

################################################
## Declare ROS messages, services and actions ##
################################################

## Generate messages in the 'msg' folder
add_message_files(
    DIRECTORY msg
    FILES
    RfidTag.msg
)

## Generate services in the 'srv' folder
add_service_files(
    DIRECTORY srv
    FILES
    WriteCard.srv
)

## Generate added messages and services with any dependencies listed here
generate_messages(
    DEPENDENCIES
    std_msgs
)

###################################
## catkin specific configuration ##
###################################

## The catkin_package macro generates cmake config files for your package
catkin_package(
    INCLUDE_DIRS
    CATKIN_DEPENDS message_runtime
    DEPENDS
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
    include
    ${catkin_INCLUDE_DIRS}
)

#############
## Install ##
#############

# all install targets should use catkin DESTINATION variables
# See http://ros.org/doc/api/catkin/html/adv_user_guide/variables.html

## Mark cpp header files for installation
install(DIRECTORY include/${PROJECT_NAME}/
    DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
    FILES_MATCHING PATTERN "*.h"
    PATTERN ".svn" EXCLUDE
)
