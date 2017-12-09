cmake_policy(SET CMP0028 NEW)
cmake_policy(SET CMP0054 NEW)
cmake_minimum_required(VERSION 2.8.3)

include(cmake/HunterGate.cmake)
HunterGate(
    URL "https://github.com/lsolanka/hunter/archive/ros-hunter.tar.gz"
    SHA1 "f92b2a7434bdcb38878a5dfef8da89ecf62a6375"
    LOCAL
)

project(roscpp_core)
hunter_add_package(Boost COMPONENTS date_time system thread)
hunter_add_package(catkin)

find_package(Boost REQUIRED COMPONENTS date_time system thread)

include_directories(roscpp_traits/include)

add_subdirectory(cpp_common)
add_subdirectory(roscpp_core)
add_subdirectory(roscpp_traits)
add_subdirectory(rostime)
add_subdirectory(roscpp_serialization)
