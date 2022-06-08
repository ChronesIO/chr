cmake_minimum_required(VERSION 3.18.3)
project(chr)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

add_library(chr src/chr)
set_target_properties(chr PROPERTIES LINKER_LANGUAGE CXX)

add_subdirectory(chr-core)
add_subdirectory(chr-mem)
add_subdirectory(chr-math)

target_link_libraries(chr PUBLIC chr-core)
target_link_libraries(chr-mem PRIVATE chr-core)
target_link_libraries(chr-math PRIVATE chr-core)