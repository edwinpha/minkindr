cmake_minimum_required(VERSION 2.8.3)
project(minkindr)

find_package(catkin REQUIRED)
find_package(Eigen3 3.3 REQUIRED NO_MODULE)
find_package(PkgConfig REQUIRED)
pkg_check_modules(glog REQUIRED libglog)
pkg_check_modules(Eigen3 REQUIRED eigen3)

find_package(Threads)

# Setup catkin package
catkin_package(
    INCLUDE_DIRS
    include
    DEPENDS
    EIGEN3
    glog)

# Add all files to show up in QtCreator.
FILE(GLOB_RECURSE LibFiles "include/*")
add_custom_target(headers SOURCES ${LibFiles})

install(DIRECTORY include/${PROJECT_NAME}/
DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION})
# export()

