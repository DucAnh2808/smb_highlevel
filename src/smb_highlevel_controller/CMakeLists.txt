cmake_minimum_required(VERSION 3.0.2)
project(smb_highlevel_controller)

# Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  rospy
  std_srvs
  sensor_msgs
  geometry_msgs
  visualization_msgs
  tf2
  tf2_ros
  tf2_geometry_msgs
  tf2_msgs
)
###################################
## catkin specific configuration ##
###################################
catkin_package(
  CATKIN_DEPENDS
    rospy
    sensor_msgs
)

# catkin_python_setup()


#############
## Install ##
#############

## Mark executable scripts (Python etc.) for installation
## in contrast to setup.py, you can choose the destination
catkin_install_python(PROGRAMS
    node/${PROJECT_NAME}
    node/stop_condition
    node/smb_highlevel_controller
   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

# Mark other files for installation (e.g. launch and bag files, etc.)
install(DIRECTORY launch config
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
