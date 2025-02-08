    cmake_minimum_required(VERSION 3.16)
project(RED)

set(CMAKE_C_STANDDARD)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(RED
    src/main.c
)

target_include_directories(
    RED
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/lib
    ${CMAKE_CURRENT_SOURCE_DIR}/src/utils
)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK REQUIRED IMPORTED_TARGET gtk+-3.0)

target_link_libraries(RED PRIVATE PkgConfig::GTK)
#i pray this works properly
