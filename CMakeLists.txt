cmake_minimum_required(VERSION 3.5)
project(kfj_ros2_demo_service_interface)

set(CMAKE_PREFIX_PATH
    $ENV{CMAKE_PREFIX_PATH}
    ${CMAKE_PREFIX_PATH}
    )

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
    set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    # use set instead of add_compile_options
    # refer to https://github.com/ros2/example_interfaces/blob/master/CMakeLists.txt#L10
    #add_compile_options(-Wall -Wextra -Wpedantic)
    set(CMAKE_CXX_FLAGS "-Wall -Wextra -Wpedantic ${CMAKE_CXX_FLAGS}")
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(
    ${PROJECT_NAME}
    srv/AddTwoInts.srv
    )

ament_package()

