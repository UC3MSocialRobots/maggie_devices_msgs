cmake_minimum_required(VERSION 2.8.3)
project(maggie_ir_controller_msgs)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS message_generation)

################################################
## Declare ROS messages, services and actions ##
################################################

## Generate messages in the 'msg' folder
add_message_files(
    DIRECTORY msg
    FILES
    TvActions.msg
)

## Generate services in the 'srv' folder
add_service_files(
    DIRECTORY srv
    FILES
    SetTvAction.srv
)

## Generate added messages and services with any dependencies listed here
generate_messages()

###################################
## catkin specific configuration ##
###################################

## The catkin_package macro generates cmake config files for your package
catkin_package(
    INCLUDE_DIRS 
    CATKIN_DEPENDS message_runtime
    DEPENDS 
)

