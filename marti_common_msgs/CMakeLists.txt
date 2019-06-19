cmake_minimum_required(VERSION 3.5)
project(marti_common_msgs)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(std_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(marti_common_msgs
  "msg/BoolStamped.msg"
  "msg/ByteArrayStamped.msg"
  "msg/DurationStamped.msg"
  "msg/Float32Stamped.msg"
  "msg/Float64Stamped.msg"
  "msg/HealthStatus.msg"
  "msg/Int16Stamped.msg"
  "msg/Int32Stamped.msg"
  "msg/Int64Stamped.msg"
  "msg/Int8Stamped.msg"
  "msg/KeyValue.msg"
  "msg/KeyValueArray.msg"
  "msg/Matrix3x3Stamped.msg"
  "msg/ServiceHeader.msg"
  "msg/StringArrayStamped.msg"
  "msg/StringStamped.msg"
  "msg/TimeStamped.msg"
  "msg/UInt16Stamped.msg"
  "msg/UInt32Stamped.msg"
  "msg/UInt64Stamped.msg"
  "msg/UInt8Stamped.msg"
  DEPENDENCIES builtin_interfaces std_msgs
)

ament_package()
