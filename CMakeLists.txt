cmake_minimum_required(VERSION 3.20)
project(planing)
set(CMAKE_CXX_STANDARD 11)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LISTS)
add_library(common
SHARED
${SRC_LISTS}
)
target_include_directories(common
PUBLIC
${PROJECT_SOURCE_DIR}/include
)

add_executable(main main.cpp)

target_include_directories(main
PUBLIC
${PROJECT_SOURCE_DIR}/include)

target_link_libraries(main
PUBLIC
common)