cmake_minimum_required(VERSION 2.8.3)
project(path_tracking)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  geometry_msgs
  tf2
  tf2_ros  
  tf 
)

## Declare a catkin package
catkin_package(

  LIBRARIES ${PROJECT_NAME}
  CATKIN_DEPENDS roscpp tf2 tf2_ros geometry_msgs
)

include_directories(include ${catkin_INCLUDE_DIRS})

add_executable(read_traj src/read_traj.cpp)
target_link_libraries(read_traj ${catkin_LIBRARIES})

add_executable(read_traj_with_callback src/read_traj_with_callback.cpp)
target_link_libraries(read_traj_with_callback ${catkin_LIBRARIES})


add_executable(current_traj src/current_traj.cpp)
target_link_libraries(current_traj ${catkin_LIBRARIES})

add_executable(exploration_autonome src/exploration_autonome.cpp)
target_link_libraries(exploration_autonome ${catkin_LIBRARIES})
