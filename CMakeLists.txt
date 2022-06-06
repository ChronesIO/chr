cmake_minimum_required(VERSION 3.18.3)
project(chr)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

add_subdirectory(chr-core)
add_subdirectory(chr-mem)

target_link_libraries(chr-mem PRIVATE chr-core)