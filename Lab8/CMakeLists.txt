cmake_minimum_required(VERSION 3.10)
project(ThreadContextSwitchCounter)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find the threads package
find_package(Threads REQUIRED)

# Find Boost program options
find_package(Boost 1.74.0 COMPONENTS program_options REQUIRED)

# Include directories
include_directories(${Boost_INCLUDE_DIR})

# Set the source directory
set(SOURCE_DIR src)

# Add the executable
add_executable(${PROJECT_NAME} ${SOURCE_DIR}/main.cpp)

# Link libraries
target_link_libraries(${PROJECT_NAME} Threads::Threads ${Boost_LIBRARIES})

