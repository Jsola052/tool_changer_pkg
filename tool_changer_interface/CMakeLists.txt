cmake_minimum_required(VERSION 3.8)
project(tool_changer_interface)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)


# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/ToolChanger.msg"
  "msg/Tool.msg"
  "srv/ToolChanger.srv"
  "srv/Tool.srv"
  "srv/GetTool.srv"
  DEPENDENCIES std_msgs

)


ament_package()
