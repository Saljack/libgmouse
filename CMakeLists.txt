cmake_minimum_required(VERSION 2.8)
project(libgmouse)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/Modules/")
find_package(libusb-1.0 REQUIRED)

set(LIBGMOUSE_H control_a4.h dips.h mouse_memory.h pairing.h system_a4.h)
set(LIBGMOUSE_SRC control_a4.cpp dpis.cpp dips.h mouse_memory.cpp pairing.cpp system_a4.cpp)
add_library(gmouse SHARED ${LIBGMOUSE_SRC})
target_link_libraries(gmouse ${LIBUSB_1_LIBRARIES})

install(TARGETS gmouse DESTINATION lib)
install(FILES ${LIBGMOUSE_H} DESTINATION include/${PROJECT_NAME})