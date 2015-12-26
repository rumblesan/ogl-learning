cmake_minimum_required(VERSION 3.0)
project(ogl-learn)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall")

include_directories(include)
file(GLOB SOURCES "src/*.c")

add_executable(ogl-learn ${SOURCES})

if(APPLE)
    include_directories(/System/Library/Framework)
    find_library(OPENGL NAMES OpenGL)
    find_library(GLUT NAMES GLUT)

    target_link_libraries(ogl-learn ${OPENGL} ${GLUT})
endif(APPLE)

