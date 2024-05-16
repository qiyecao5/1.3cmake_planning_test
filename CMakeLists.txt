# 一.最外面的CMakeLists.txt
cmake_minimum_required(VERSION 3.29.0) # 这个就是设置你cmake所需要的最小版本

# 这样写 让你的项目更像一个项目 
project(planning    # 就是你这个项目的名字
    VERSION 0.0.1   # 这一行是版本
    DESCRIPTION " a demo of cmake planning"  # 这一行是描述
    HOMEPAGE_URL "https://github.com/qiyecao5/cmake_planning_demo"  # 这行是github的项目链接把最后.git删掉
    LANGUAGES CXX   # CXX 表示C++, 指定语言
)  

set(CMAKE_CXX_STANDARD 17) # 指定C++的标准在11以及以上


# 把动态库和exe都指定到bin目录下面
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)  

# 这里设置的变量,会传递到下面的那个src子目录里面,
# 也就说 子目录里面里面的CMakeLists.txt 也是可以用到父目录里面的变量的,相当于C++里面的类与类继承,你可以简单的这么理解
set(Process_Dir ${CMAKE_SOURCE_DIR}/src/process)    # 设置 路径变量
set(PNC_Map_Dir ${CMAKE_SOURCE_DIR}/src/pnc_map)    # 设置 pnc_map路径的变量

# 添加子目录
# 这个命令就是 找src目录里面的CMakeLists.txt,只要你有这个文件 就能找到
add_subdirectory(src)