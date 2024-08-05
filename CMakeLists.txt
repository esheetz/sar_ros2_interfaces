cmake_minimum_required(VERSION 3.8)
project(sar_ros2_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

# set action files
#set(act_files
#  "action/TODO.action"
#)

# set message files
set(msg_files
  "msg/DetectedHazards.msg"
)

# set service files
#set(srv_files
#  "srv/TODO.srv"
#)

# generate messages and services
rosidl_generate_interfaces(${PROJECT_NAME}
#  ${act_files}
  ${msg_files}
#  ${srv_files}
  DEPENDENCIES
  std_msgs
)

ament_package()
