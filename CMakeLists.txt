cmake_minimum_required(VERSION 3.10)
project(OpenGLProject)

# C++17 or above recommended
set(CMAKE_CXX_STANDARD 17)

# Explicit Homebrew include and link directories for GLFW/GLM
include_directories(
    libs/glad/include
    /opt/homebrew/include
)

link_directories(
    /opt/homebrew/lib
)

# Source files
add_executable(OpenGLProject
    main.cpp
    libs/glad/src/glad.c
)

# Link GLFW, OpenGL (Homebrew)
target_link_libraries(OpenGLProject
    glfw
    "-framework OpenGL"
)
