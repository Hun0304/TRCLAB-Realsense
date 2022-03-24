cmake_minimum_required(VERSION 3.21)
project(TRCLab-RealSense)
set(CMAKE_CXX_STANDARD 14)

find_package(OpenCV REQUIRED)

add_executable(TRCLab-RealSense RealSense.cpp)

include_directories(realsense2 libs/librealsense/include)
if (OpenCV_FOUND)
    include_directories(${OpenCV_INCLUDE_DIRS})
    link_directories(${OpenCV_LIB_DIR})
    target_link_libraries(TRCLab-RealSense ${OpenCV_LIBS})
endif ()
