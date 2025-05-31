cmake_minimum_required(VERSION 3.21)

# Set default build type to release
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "" FORCE)
endif()

# Generate compile_commands.json by default
if(NOT CMAKE_EXPORT_COMPILE_COMMANDS)
    set(CMAKE_EXPORT_COMPILE_COMMANDS "YES" CACHE STRING "" FORCE)
endif()

project(example)

file(GLOB_RECURSE cpp_src src/*.cpp)
add_executable(example ${cpp_src})

if(NOT MSVC)
    target_compile_options(example PRIVATE -Wall -pedantic -Wextra -Werror)
else()
    target_compile_options(example PRIVATE /WX)
endif()

target_compile_features(example PUBLIC cxx_std_23)
target_include_directories(example PRIVATE src)
