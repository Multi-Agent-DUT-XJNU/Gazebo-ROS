cmake_minimum_required(VERSION 2.8.3)
project(volta_simulation)

find_package(catkin REQUIRED COMPONENTS roslaunch)

catkin_package ()

install(
  DIRECTORY launch worlds
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
