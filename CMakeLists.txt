cmake_minimum_required(VERSION 2.8.3)
project(case_study_2)

find_package(catkin REQUIRED
                    sensor_msgs
                    roscpp
	            std_msgs
                    cmake_modules
                    roslib
	            moveit_core
    	            moveit_ros_planning
	            moveit_ros_planning_interface
                    moveit_visual_tools
                    tf
                    geometry_msgs
                    ur_modern_driver
                    apriltag_ros
)

find_package(Boost REQUIRED system filesystem date_time thread)

catkin_package(
  CATKIN_DEPENDS moveit_core moveit_ros_planning_interface moveit_visual_tools
)

find_package(Eigen REQUIRED)

include_directories(include ${catkin_INCLUDE_DIRS})

catkin_install_python(PROGRAMS scripts/stow_ur5 scripts/open_3fgripper scripts/close_3fgripper DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

install(DIRECTORY config launch scripts
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

