cmake_minimum_required(VERSION 3.21)

# Set default build type to release
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "" FORCE)
endif()

project(example)

file(GLOB_RECURSE cpp_src src/*.cpp)
set_property(SOURCE ${cpp_src} PROPERTY COMPILE_FLAGS "-Wno-unused")
add_executable(example ${cpp_src})

target_compile_options(example PRIVATE -Wall -Wextra -pedantic)
target_compile_features(example PUBLIC cxx_std_23)
target_include_directories(example PRIVATE src)
