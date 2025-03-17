cmake_minimum_required(VERSION 3.3)
 
# Project Name
project(displayinfo-soc)
 
# Set Library Name
set(LIB_NAME displayinfo-soc)
 
# Set C++ Standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
 
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake")
 
 
include_directories(include)
include_directories(${STAGING_INCDIR})
 
 
# Add Include Directories
include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)
 
# Source Files
set(SRC_FILES
    SoC_abstraction.cpp
)
 
# Create Shared Library
add_library(${LIB_NAME} SHARED ${SRC_FILES})
 
# Set Library Output Name
set_target_properties(${LIB_NAME} PROPERTIES OUTPUT_NAME "displayinfo-soc")

# Link Required Libraries (if any)
target_link_libraries(${LIB_NAME}
    PRIVATE
)
 
message("Library ${LIB_NAME} built successfully")
