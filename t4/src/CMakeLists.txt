cmake_minimum_required(VERSION 3.16)

add_executable(t4 main.cpp)
# 添加头文件搜索路径
include_directories(/home/barret/t3/include/t3)

# 查找lib文件
# find_library(LIB_PATH libt3.a /home/barret/t3/lib) # 静态库
find_library(LIB_PATH libt3.so /home/barret/t3/lib) # 动态库
if(NOT LIB_PATH)
    MESSAGE(FATAL_ERROR "libt3 not found")
endif(NOT LIB_PATH)

message(STATUS "lib path" ${LIB_PATH})
# 链接库
target_link_libraries(t4 ${LIB_PATH})
