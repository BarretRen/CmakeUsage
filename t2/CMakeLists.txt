cmake_minimum_required(VERSION 3.16)

project(t2)
message(STATUS " binary path is" ${PROJECT_BINARY_DIR})
message(STATUS " source path is" ${PROJECT_SOURCE_DIR})

set(CMAKE_CXX_STANDARD 17)
# 添加子目录的cmake
add_subdirectory(src bin)

# 安装readme和版权文件
install(FILES COPYRIGHT README DESTINATION share/doc/cmake/t2)
# 安装sh文件
install(PROGRAMS runhello.sh DESTINATION bin)
# 安装doc hello.txt
install(DIRECTORY doc/ DESTINATION share/doc/cmake/t2)
# 安装可执行文件
install(PROGRAMS ${PROJECT_BINARY_DIR}/bin/t2 DESTINATION bin)
