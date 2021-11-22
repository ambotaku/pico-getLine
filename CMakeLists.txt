cmake_minimum_required(VERSION 3.12)

include($ENV{PICO_SDK_PATH}/external/pico_sdk_import.cmake)

project(getline 
    LANGUAGES C CXX ASM 
    VERSION 1.0 
    DESCRIPTION "Serial I/O Test")


set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pico_sdk_init()

add_executable(${CMAKE_PROJECT_NAME}
  getline.cpp
)

add_definitions(-DTEST_GETLINE)


target_link_libraries(${CMAKE_PROJECT_NAME}
  pico_stdlib
)

pico_enable_stdio_uart(${CMAKE_PROJECT_NAME} 1)
pico_enable_stdio_usb(${CMAKE_PROJECT_NAME} 0)
pico_add_extra_outputs(${CMAKE_PROJECT_NAME})
