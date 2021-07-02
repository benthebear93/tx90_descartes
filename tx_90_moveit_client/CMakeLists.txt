cmake_minimum_required(VERSION 3.0.2)

project(tx_90_moveit_client)

find_package(catkin REQUIRED COMPONENTS
  roslib
  descartes_core
  descartes_moveit
  descartes_trajectory
  descartes_planner
  descartes_utilities
  trajectory_msgs

  moveit_commander
  rospy
  roscpp
  geometry_msgs
  tf_conversions
  eigen_conversions
)

catkin_package(INCLUDE_DIRS CATKIN_DEPENDS roscpp tf)

find_package(roslaunch)

include_directories(include ${catkin_INCLUDE_DIRS})

add_executable(example1 src/example1.cpp)
target_link_libraries(example1 ${catkin_LIBRARIES})
add_dependencies(example1 example1)