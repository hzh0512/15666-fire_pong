cmake_minimum_required(VERSION 3.14)

set(CMAKE_VERBOSE_MAKEFILE ON)

include_directories(.)
include_directories(../nest-libs/linux/SDL2/include/SDL2)
include_directories(../nest-libs/linux/glm/include)
include_directories(../nest-libs/linux/libpng/include)

link_directories(../nest-libs/linux/SDL2/lib)
link_directories(../nest-libs/linux/libpng/lib)
link_libraries(SDL2 GL m dl pthread rt png z)

add_definitions(-no-pie -std=c++11 -g -Wall -Werror -D_REENTRANT)
add_link_options(-no-pie)

aux_source_directory(. CUR)
add_executable(dash_pong ${CUR})
