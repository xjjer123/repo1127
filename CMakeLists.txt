# 指定 CMake 最低版本要求
cmake_minimum_required(VERSION 3.10)

# 定义项目名称和版本
project(MyProject VERSION 1.0.0 LANGUAGES CXX)

# 设置 C++ 标准（推荐 C++14 或更高）
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# 添加可执行文件（假设源文件在 src/ 目录）
add_executable(my_app
    src/main.cpp
    src/utils.cpp
)

# 添加头文件目录
target_include_directories(my_app
    PUBLIC
        ${PROJECT_SOURCE_DIR}/include
)

# 链接第三方库（示例）
# target_link_libraries(my_app PRIVATE some_library)

# 安装配置（可选）
install(TARGETS my_app
    RUNTIME DESTINATION bin
)

# 测试配置（可选）
enable_testing()
add_test(NAME my_test COMMAND my_app --test)
