# toplevel CMakeLists.txt for a catkin workspace
# catkin/cmake/toplevel.cmake
cmake_policy(SET CMP0028 NEW)
cmake_minimum_required(VERSION 2.8.3)

include(cmake/HunterGate.cmake)
HunterGate(
    URL "https://github.com/lsolanka/hunter/archive/ros-hunter.tar.gz"
    SHA1 "36f40fa452f70dafe1a4d99c9f15bfbe9ea185f9"
    LOCAL
)

project(roscpp_core)
hunter_add_package(Boost COMPONENTS date_time system thread)
hunter_add_package(catkin)

include_directories(roscpp_traits/include)

add_subdirectory(cpp_common)
add_subdirectory(roscpp_core)
add_subdirectory(roscpp_traits)
add_subdirectory(rostime)
add_subdirectory(roscpp_serialization)
