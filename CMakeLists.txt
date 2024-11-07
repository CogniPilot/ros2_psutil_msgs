cmake_minimum_required(VERSION 3.8)
project(ros2_psutil_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

set(msg_files
  "msg/Psutil.msg"
  "msg/PsutilMemory.msg"
  "msg/PsutilMemoryStamped.msg"
  "msg/PsutilNetworkAddress.msg"
  "msg/PsutilNetworkDevice.msg"
  "msg/PsutilNetworkStamped.msg"
  "msg/PsutilNetworkState.msg"
  "msg/PsutilNetworkStats.msg"
  "msg/PsutilProcessor.msg"
  "msg/PsutilProcessorStamped.msg"
  "msg/PsutilProcessorFrequency.msg"
  "msg/PsutilProcessorPercent.msg"
  "msg/PsutilTemperature.msg"
  "msg/PsutilTemperatureDevice.msg"
  "msg/PsutilTemperatureStamped.msg"
)
rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  DEPENDENCIES std_msgs
  ADD_LINTER_TESTS
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()
