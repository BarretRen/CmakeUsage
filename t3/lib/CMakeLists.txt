cmake_minimum_required(VERSION 3.16)

set(CMAKE_CXX_STANDARD 17)

message(STATUS "the library output path is" ${LIBRARY_OUTPUT_PATH})

# 编译动态库，不是executable
add_library(t3 SHARED hello.cpp)
# 设置动态库版本号
set_target_properties(t3 PROPERTIES VERSION 1.2 SOVERSION 1)

# 编译静态库
add_library(t3_static STATIC hello.cpp)
# 重命名静态库
set_target_properties(t3_static PROPERTIES OUTPUT_NAME "t3")

# 安装库文件
install(TARGETS t3 t3_static
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib)
# 安装头文件
install(FILES hello.hpp DESTINATION include/t3)
