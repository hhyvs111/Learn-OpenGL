cmake_minimum_required(VERSION 3.12)
project(Learn-OpenGL)

set(CMAKE_CXX_STANDARD 14)
# 添加头文件
if (APPLE)
    set(GLEW_H /usr/local/Cellar/glew/2.1.0/include/GL)
    set(GLFW_H /usr/local/Cellar/glfw/3.2.1/include/GLFW)
    set(GLAD_H /usr/local/include/glad)
    include_directories(${GLEW_H} ${GLFW_H} ${GLAD_H})

    # 添加目标链接
    set(GLEW_LINK /usr/local/Cellar/glew/2.1.0/lib/libGLEW.2.1.dylib)
    set(GLFW_LINK /usr/local/Cellar/glfw/3.2.1/lib/libglfw.3.dylib)
    link_libraries(${OPENGL} ${GLEW_LINK} ${GLFW_LINK})
endif()
# 执行编译命令
#"src/1.start/1.1.helloWindow/helloWindow.cpp"
set(SOURCE_FILES "src/glad.c" "src/1.start/1.2.helloTriangle/helloTriangle.cpp")
add_executable(Learn-OpenGL ${SOURCE_FILES})
#if (APPLE)
#    target_link_libraries(Learn-OpenGL "-framework OpenGL")
#    target_link_libraries(Learn-OpenGL "-framework GLUT")
#endif()
