cmake_minimum_required(VERSION 2.8)

include(FindPkgConfig)

set(CMAKE_VERBOSE_MAKEFILE on)
set(CMAKE_CXX_FLAGS "-std=c++11 -Wall -Werror -Wl,--as-needed")

pkg_check_modules(LIBVIDEOBOX REQUIRED videobox)
include_directories(./ $LIBVIDEOBOX_INCLUDE_DIRS})
link_libraries(${LIBVIDEOBOX_LIBRARIES})

add_executable(demo_video_002 demo_main.cpp)

install(TARGETS demo_video_002 DESTINATION bin)
