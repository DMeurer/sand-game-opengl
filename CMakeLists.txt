cmake_minimum_required(VERSION 3.29)
project(sand_game)

find_package(OpenGL REQUIRED)

set(CMAKE_CXX_STANDARD 26)

# Including GLFW
add_subdirectory(glfw)
include_directories(glfw/include)

# Including GLAD
include_directories(glad/include)

set(SOURCE_FILES main.cpp glad/src/glad.c)

add_executable(${CMAKE_PROJECT_NAME} ${SOURCE_FILES})

# Linking GLFW and OGL
target_link_libraries(${CMAKE_PROJECT_NAME} glfw ${GLFW_LIBRARIES} ${OPENGL_LIBRARY})
