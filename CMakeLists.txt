cmake_minimum_required(VERSION 2.8.3)


include(cmake/base.cmake)
include(cmake/ros.cmake)

set(PROJECT_NAME tiago_data)
set(PROJECT_DESCRIPTION SoT data for Tiago)
set(PROJECT_URL "http://github.com/stack-of-tasks/tiago_data")

setup_project()

find_package(catkin REQUIRED)

catkin_package()

foreach(dir gazebo Media meshes robots urdf config)
    install(DIRECTORY ${dir}/
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)

#############
## Testing ##
#############

setup_project_finalize()
