cmake_minimum_required(VERSION 3.12)
project(Learn-OpenGL)

set(CMAKE_CXX_STANDARD 14)
# 添加头文件
    include_directories(${CMAKE_SOURCE_DIR}/includes)
    # 添加目标链接
    set(GLEW_LINK /usr/local/Cellar/glew/2.1.0/lib/libGLEW.2.1.dylib)
    set(GLFW_LINK /usr/local/Cellar/glfw/3.2.1/lib/libglfw.3.dylib)
    link_libraries(${OPENGL} ${GLEW_LINK} ${GLFW_LINK})
# 执行编译命令
#"src/1.start/1.1.helloWindow/helloWindow.cpp"
set(SOURCE_FILES "src/glad.c" src/1.start/1.3.shader/shader_class.cpp)
add_executable(Learn-OpenGL ${SOURCE_FILES})
