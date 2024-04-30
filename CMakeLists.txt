cmake_minimum_required(VERSION 3.2)
project(SLAMProject)

#-------------------------------------------------------------------
# Build type. Default is Release
if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

message("Build type: " ${CMAKE_BUILD_TYPE})

#-------------------------------------------------------------------
# C++ flags and standard. Using C++20
set(CMAKE_CXX_FLAGS "-Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")
set(CMAKE_CXX_STANDARD 20)

#-------------------------------------------------------------------
# Executables should be created in bin directory
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin")

#-------------------------------------------------------------------
# Package dependences. If these fail, check README.md for installation
find_package(GTSAM REQUIRED)
find_package(Boost 1.70.0 REQUIRED system filesystem)

# Define executables. Only one in our case.
add_executable(
    main
    src/main.cpp
)
target_link_libraries(
    main
    gtsam
    Boost::program_options
)
target_include_directories(main PRIVATE include)