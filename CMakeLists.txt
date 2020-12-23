cmake_minimum_required(VERSION 2.8.3)
project(better_enums)
find_package(catkin REQUIRED)
catkin_package(
  INCLUDE_DIRS include)
install(DIRECTORY include/
  DESTINATION ${CATKIN_GLOBAL_INCLUDE_DESTINATION}
  FILES_MATCHING PATTERN "*.h"
)
