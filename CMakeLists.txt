cmake_minimum_required(VERSION 3.10.2)
project(cmake-cpp-example)

add_subdirectory(glad/)
find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})

include_directories(include build/glad/include)

file(GLOB SOURCES "src/*.cpp", "build/glad/src/*.c")

add_executable(main ${SOURCES})
target_link_libraries(main glad)
target_link_libraries(main ${SDL2_LIBRARIES})
target_link_libraries(main dl)
