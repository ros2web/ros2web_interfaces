cmake_minimum_required(VERSION 3.8)
project(ros2web_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)


rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/ContentType.msg"
  "msg/HTTPStatusCode.msg"

  "msg/StatusMsg.msg"
  "msg/StatusType.msg"

  "msg/WSMsgData.msg"
  "msg/WSMsgType.msg"
  "msg/WSMsg.msg"

  "srv/HTTP.srv"
  "srv/ServerInfo.srv"
)

ament_export_dependencies(rosidl_default_runtime)
ament_package()
