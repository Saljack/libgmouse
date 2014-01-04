cmake_minimum_required(VERSION 2.8)
project(libgmouse)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/Modules/")
find_package(libusb-1.0 REQUIRED)

set(LIBGMOUSE_SRC main.cpp control_a4.cpp dpis.cpp dips.h mouse_memory.cpp pairing.cpp system_a4.cpp)
add_library(libgmouse SHARED ${LIBGMOUSE_SRC})
target_link_libraries(libgmouse ${LIBUSB_1_LIBRARIES})
# target_link_libraries(libgmouse 
# install(TARGETS libgmouse RUNTIME DESTINATION bin)