cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

add_definitions(-std=c++2a)

set(CXX_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS, "${CXX_FLAGS}")
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /std:c++20")

project(camera_fusion)


# Edit this line for your environments...
#SET(OpenCV_DIR "D:/github_repository/vcpkg/installed/x64-windows/share/opencv")

# Check the version of the OpenCV library...
find_package(OpenCV 4.5 REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})
link_directories(${OpenCV_LIBRARY_DIRS})
add_definitions(${OpenCV_DEFINITIONS})

# Executable for create matrix exercise
add_executable (2D_feature_tracking src/matching2D_Student.cpp src/MidTermProject_Camera_Student.cpp)
target_link_libraries (2D_feature_tracking ${OpenCV_LIBRARIES})
