cmake_minimum_required(VERSION 2.8.3)
project(tesseract_msgs)

add_compile_options(-std=c++11 -Wall -Wextra)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
  sensor_msgs
  geometry_msgs
  shape_msgs
  octomap_msgs
  trajectory_msgs
)

add_message_files(
  DIRECTORY msg
  FILES
    AttachableObject.msg
    AttachedBodyInfo.msg
    VisualGeometry.msg
    CollisionGeometry.msg
    TesseractState.msg
    ObjectColor.msg
    Trajectory.msg
    ContactResult.msg
    ContactResultVector.msg
)

add_service_files(
  DIRECTORY srv
  FILES
    ModifyTesseractEnv.srv
    ComputeContactResultVector.srv
)

generate_messages(
  DEPENDENCIES
    std_msgs
    sensor_msgs
    geometry_msgs
    shape_msgs
    octomap_msgs
    trajectory_msgs
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
    std_msgs
    sensor_msgs
    geometry_msgs
    shape_msgs
    octomap_msgs
    trajectory_msgs
)
