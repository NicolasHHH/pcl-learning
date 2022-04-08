cmake_minimum_required(VERSION 3.3) 
project(00base)
find_package(PCL 1.2 REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

#这句话告诉CMake从单个源文件write_pcd建立一个可执行文件
add_executable(pcd_write pcd_write.cpp)
#虽然包含了PCL的头文件，因此编译器知道我们现在访问所用的方法，我们也需要让链接器知道所链接的库，PCL找到库文件由
#PCL_COMMON_LIBRARIES变量指示，通过target_link_libraries这个宏来出发链接操作
target_link_libraries (pcd_write ${PCL_LIBRARIES}) # 