cmake_minimum_required(VERSION 2.8.3)

include(cmake/HunterGate.cmake)
HunterGate(
    URL "https://github.com/lsolanka/hunter/archive/v0.19.210-1.tar.gz"
    SHA1 "dcf5bbcdd34c5db52f5468105c7949ae68c57532"
)

project(roscpp_core)
hunter_add_package(Boost COMPONENTS date_time system thread)
hunter_add_package(ros-catkin)

find_package(Boost REQUIRED COMPONENTS date_time system thread)

add_subdirectory(cpp_common)
add_subdirectory(roscpp_core)
add_subdirectory(roscpp_traits)
add_subdirectory(rostime)
add_subdirectory(roscpp_serialization)
