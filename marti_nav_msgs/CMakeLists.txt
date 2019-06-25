cmake_minimum_required(VERSION 3.5)
project(marti_nav_msgs)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(geographic_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(marti_common_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(std_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Command.msg"
  "msg/GridMap.msg"
  "msg/LeadVehicle.msg"
  "msg/Obstacle.msg"
  "msg/ObstacleArray.msg"
  "msg/PathPlanning.msg"
  "msg/Route.msg"
  "msg/RouteArray.msg"
  "msg/RouteOffset.msg"
  "msg/RoutePoint.msg"
  "msg/RoutePosition.msg"
  "msg/RouteSpeed.msg"
  "msg/RouteSpeedArray.msg"
  "msg/TeleopState.msg"
  "msg/TrackedObject.msg"
  "msg/TrackedObjectArray.msg"
  "msg/VehicleControl.msg"
  "msg/Wgs84Sample.msg"
  "srv/DeleteRoute.srv"
  "srv/GetRoute.srv"
  "srv/GetRouteList.srv"
  "srv/PlanRoute.srv"
  "srv/SaveRecordedRoute.srv"
  "srv/SaveRoute.srv"
  "srv/SetRoute.srv"
  "srv/UpdateRouteMetadata.srv"
  DEPENDENCIES
  builtin_interfaces
  std_msgs
  geographic_msgs
  geometry_msgs
  marti_common_msgs
  sensor_msgs
)

ament_package()
