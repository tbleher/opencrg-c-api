cmake_minimum_required(VERSION 3.16.0)

project(OpenCRG LANGUAGES C VERSION 1.1.2)

if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
    # Build with "RelWithDebInfo" by default
    set(CMAKE_BUILD_TYPE "RelWithDebInfo" CACHE STRING "Choose the type of build." FORCE)
    # Set the possible values of build type for cmake-gui
    set_property(CACHE CMAKE_BUILD_TYPE PROPERTY STRINGS "Debug" "Release" "MinSizeRel" "RelWithDebInfo")
endif()

set(C_FILES
    src/crgContactPoint.c
    src/crgEvalpk.c
    src/crgEvaluv2xy.c
    src/crgEvalxy2uv.c
    src/crgEvalz.c
    src/crgLoader.c
    src/crgMgr.c
    src/crgMsg.c
    src/crgOptionMgmt.c
    src/crgPortability.c
    src/crgStatistics.c)

add_library(${PROJECT_NAME} STATIC ${C_FILES})

target_include_directories(${PROJECT_NAME} PUBLIC inc)
set_property(TARGET ${PROJECT_NAME} PROPERTY C_STANDARD 11)

if(UNIX)
    target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra)
endif()
