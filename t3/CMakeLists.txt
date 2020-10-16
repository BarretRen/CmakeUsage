cmake_minimum_required(VERSION 3.16)

project(t3)
message(STATUS " binary path is" ${PROJECT_BINARY_DIR})
message(STATUS " source path is" ${PROJECT_SOURCE_DIR})

# 添加子目录的cmake
add_subdirectory(lib)
