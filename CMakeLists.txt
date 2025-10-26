cmake_minimum_required(VERSION 4.0)
project(malergeist)

set(CMAKE_CXX_STANDARD 20)

# Add source files
set(SOURCES
        src/main.cpp
        third_party/glad/src/glad.c
)

add_executable(malergeist ${SOURCES})

# Include directories
target_include_directories(malergeist PRIVATE
        third_party/glad/include
)

# Link GLFW (system)
find_package(glfw3 3.3 REQUIRED)
find_package(OpenGL REQUIRED)



target_link_libraries(malergeist glfw OpenGL::GL)