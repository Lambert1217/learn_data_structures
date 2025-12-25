cmake_minimum_required(VERSION 3.26.0)

project(learn_data_structures)

set(TARGET_NAME ${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

file(GLOB_RECURSE SOURCE_FILES "./src/*.cpp")
file(GLOB_RECURSE HEADER_FILES "./include/*.h" "./include/*.hpp")

add_library(${TARGET_NAME} ${SOURCE_FILES} ${HEADER_FILES})

target_include_directories(${TARGET_NAME} PUBLIC "./include")

set(ENABLE_TEST OFF)

if(CMAKE_SOURCE_DIR STREQUAL CMAKE_CURRENT_LIST_DIR)
    set(ENABLE_TEST ON)
endif()

if(ENABLE_TEST)
    add_subdirectory(test)
endif()
