cmake_minimum_required(VERSION 3.21)
project(OpenGLProject CXX)

set(CMAKE_CXX_STANDARD 14)

find_package(OpenGL REQUIRED)
include_directories( ${OPENGL_INCLUDE_DIRS} )

set( GLFW_BUILD_DOCS OFF CACHE BOOL  "GLFW lib only" )
set( GLFW_INSTALL OFF CACHE BOOL  "GLFW lib only" )

add_subdirectory(glfw)

set(SOURCE_FILES
        src/Application.cpp
        )


add_executable(OpenGLProject ${SOURCE_FILES})

target_link_libraries(OpenGLProject ${OPENGL_LIBRARIES} glfw)