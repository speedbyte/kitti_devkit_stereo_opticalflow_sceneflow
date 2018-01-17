cmake_minimum_required(VERSION 3.8)
project(kitti_devkit_stereo_opticalflow_sceneflow)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -ggdb3")

file(GLOB KITTI_HEADERS "*.h")

add_library(kitti evaluate_flow.cpp)
target_link_libraries(kitti png)

install(TARGETS kitti DESTINATION lib )
install(FILES ${KITTI_HEADERS} DESTINATION include/kitti)
