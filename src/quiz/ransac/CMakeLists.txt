cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

add_definitions(-std=c++11)

set(CXX_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS, "${CXX_FLAGS}")

project(playback)

find_package(PCL 1.2 REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})
list(REMOVE_ITEM PCL_LIBRARIES "vtkproj4")


add_executable (ransac_line ransac_line.cpp ../../render/render.cpp)
target_link_libraries (ransac_line ${PCL_LIBRARIES})

add_executable (ransac_plane ransac_plane.cpp ../../render/render.cpp)
target_link_libraries (ransac_plane ${PCL_LIBRARIES})
