cmake_minimum_required(VERSION 3.0.2)

set(PROJECT_NAME ProjTestWithGDB)
project(${PROJECT_NAME} CXX)

# inform of our project
set(APP_TARGET_NAME main)
message(STATUS "Building ${APP_TARGET_NAME}...")

# add all cpp files as sources
file(GLOB SOURCES "*.cpp")

# add exe
add_executable(${APP_TARGET_NAME} ${SOURCES})

# inform of install dir
install(TARGETS ${APP_TARGET_NAME} DESTINATION bin)