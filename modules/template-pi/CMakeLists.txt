cmake_minimum_required(VERSION 2.6)

project(template-pc)
set(exe_name "template-pi")
include(../../flags.cmake)

enable_testing()

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

find_library(WIRINGPI_LIBRARIES NAMES wiringPi)
find_path(WIRINGPI_INCLUDE_DIRS NAMES wiringPi.h)
include_directories(${WIRINGPI_INCLUDE_DIRS})

set(sources
    src/main.cpp)

add_executable(${exe_name} ${sources})
target_link_libraries(${exe_name} ${WIRINGPI_LIBRARIES})
