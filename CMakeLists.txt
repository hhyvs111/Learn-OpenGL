cmake_minimum_required(VERSION 3.12)
project(Learn-OpenGL)

set(CMAKE_CXX_STANDARD 14)
# 添加头文件
set(GLEW_H /usr/local/Cellar/glew/2.1.0/include/GL)
set(GLFW_H /usr/local/Cellar/glfw/3.2.1/include/GLFW)
include_directories(${GLEW_H} ${GLFW_H})

# 添加目标链接
set(GLEW_LINK /usr/local/Cellar/glew/2.1.0/lib/libGLEW.2.1.dylib)
set(GLFW_LINK /usr/local/Cellar/glfw/3.2.1/lib/libglfw.3.dylib)
link_libraries(${OPENGL} ${GLEW_LINK} ${GLFW_LINK})

# 执行编译命令
set(SOURCE_FILES main.cpp)
add_executable(Learn-OpenGL ${SOURCE_FILES})
if (APPLE)
    target_link_libraries(Learn-OpenGL "-framework OpenGL")
    target_link_libraries(Learn-OpenGL "-framework GLUT")
endif()