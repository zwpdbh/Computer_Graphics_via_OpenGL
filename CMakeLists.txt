cmake_minimum_required(VERSION 3.9)
# This must be done before any language is set (ie before any project() or enable_language() command).
set(CMAKE_C_COMPILER "/usr/local/opt/llvm/bin/clang")
set(CMAKE_CXX_COMPILER "/usr/local/opt/llvm/bin/clang++")

project(Computer_Graphics_via_OpenGL)

# set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
# cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=ON -H. -Bbuild
set(CMAKE_CXX_STANDARD 11)
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

# set the output folder where your program will be created
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH  ${CMAKE_BINARY_DIR})
# CMAKE_SOURCE_DIR is where cmake was started, the top level source directory
# CMAKE_BINARY_DIR is the same as CMAKE_SOURCE_DIR, otherwise this is the top level directory of your build tree

include_directories("${PROJECT_SOURCE_DIR}")
# contains the full path to the root of your project source directory (for example, to the nearest directory where
# CMakeLists.txt contains the PROJECT() command)

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)

# set include header file search path
include_directories("/usr/local/include/" "/usr/include")

# set link dynamic shared lib search path 
link_directories("/usr/local/lib/" "/usr/lib")
link_directories("/usr/local/Cellar/glew/2.1.0/lib/")

# set linked dynamic libraries
link_libraries("GLEW")
link_libraries("glfw")
link_libraries("glut")
link_libraries(${OPENGL_LIBRARY})

add_subdirectory(chapter_02)
