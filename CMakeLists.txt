cmake_minimum_required(VERSION 2.8.3)
project(imu_read)

find_package(catkin REQUIRED)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  geometry_msgs
  sensor_msgs
  serial
  std_msgs
  std_srvs
  tf
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES imu_read
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

include_directories(
  include ${catkin_INCLUDE_DIRS}
)


add_executable(imu_read
  src/imu_read.cpp
)
add_dependencies(imu_read ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})
target_link_libraries(imu_read
  ${catkin_LIBRARIES}
)
