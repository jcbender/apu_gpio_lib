cmake_minimum_required(VERSION 3.0)

project(apu2_gpio C)

set(VERSION_MAJOR 1)
set(VERSION_MINOR 0)
set(VERSION_PATCH 1)
set(VERSION_STRING ${VERSION_MAJOR}.${VERSION_MINOR}.${VERSION_PATCH})

set(BUILD_SHARED_LIBS OFF CACHE BOOL "Build shared lib")

set(LIB_SRC src/apu2_gpio.c)

configure_file(${CMAKE_CURRENT_SOURCE_DIR}/src/version.h.in ${CMAKE_CURRENT_BINARY_DIR}/version.h)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_CURRENT_BINARY_DIR})

add_library(${PROJECT_NAME} ${LIB_SRC})

set_target_properties(${PROJECT_NAME} PROPERTIES
                      VERSION ${VERSION_STRING}
                      SOVERSION ${VERSION_MAJOR})

add_subdirectory (example)
