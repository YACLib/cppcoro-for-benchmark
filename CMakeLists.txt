cmake_minimum_required(VERSION 3.12)
project(cppcoro LANGUAGES CXX)

if(NOT "${CMAKE_CXX_STANDARD}")
  message("C++ version not set. Defaulting to CMAKE_CXX_STANDARD=20")
  set(CMAKE_CXX_STANDARD 20)
endif()

set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

list(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake")

add_subdirectory(lib)

configure_file(cmake/cppcoroConfig.cmake
    "${PROJECT_BINARY_DIR}/cppcoro/cppcoroConfig.cmake"
    COPYONLY)
