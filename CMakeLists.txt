cmake_minimum_required(VERSION 2.8.3)
project(jetto_msgs)

## Compile as C++11, supported in ROS Kinetic and newer
add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  # messages
  std_msgs
  sensor_msgs
  message_generation
)

##############
## Messages ##
##############

add_message_files(
  FILES
  RawMotor.msg
  BatteryStatus.msg
  Point2D.msg
  PropVelocity.msg
  Flow.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

###################################
## catkin specific configuration ##
###################################
catkin_package(
   CATKIN_DEPENDS sensor_msgs std_msgs
   CATKIN_DEPENDS message_runtime
)
