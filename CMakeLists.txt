cmake_minimum_required(VERSION 3.14)
project(imgui_dojo)

set(CMAKE_CXX_STANDARD 14)

include_directories(D:/playground/glfw-3.3/include D:/playground/glad/include D:/playground/imgui/examples/libs/gl3w)
# Please config all dirs accordingly
# ref: https://learnopengl-cn.github.io/01%20Getting%20started/02%20Creating%20a%20window/#glfw
# glfw3: https://www.glfw.org/download.html
# glad: https://glad.dav1d.de/

link_libraries(opengl32.dll)
# windows default lib

link_directories(D:/playground/glfw-3.3/lib-mingw-w64)
# glfw3, same as above

aux_source_directory(. DIR_SRCS)
# copy those dependencies from imgui
# dear imgui: https://github.com/ocornut/imgui

add_executable(imgui_dojo ${DIR_SRCS})

target_link_libraries(${PROJECT_NAME} glfw3)
# link glfw3 lib