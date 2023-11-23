cmake_minimum_required(VERSION 3.5)
project(minkindr)

find_package(ament_cmake REQUIRED)
find_package(Eigen3 3.3 REQUIRED NO_MODULE)
find_package(PkgConfig REQUIRED)
pkg_check_modules(glog REQUIRED libglog)
pkg_check_modules(Eigen3 REQUIRED eigen3)

find_package(Threads)

# Setup catkin package
# catkin_package(
#     INCLUDE_DIRS
#     include
#     DEPENDS
#     EIGEN3
#     glog)

# catkin_add_gtest(${PROJECT_NAME}_tests 
#   test/test-main.cc
#   test/test-rotation.cc
#   test/test-sim3.cc
#   test/test-transformation.cc
#   test/test-transformation-2d.cc
# )
# target_link_libraries(${PROJECT_NAME}_tests ${catkin_LIBRARIES} 
#                                             ${CMAKE_THREAD_LIBS_INIT}
#                                             ${EIGEN3_INCLUDE_DIRS})

# Add all files to show up in QtCreator.
FILE(GLOB_RECURSE LibFiles "include/*")
add_custom_target(headers SOURCES ${LibFiles})

install(DIRECTORY include/
DESTINATION include)
# export()
ament_package()
