cmake_minimum_required(VERSION 3.13)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
include(pico_sdk_import.cmake)
project(pico_serprog)

pico_sdk_init()

add_executable(pico_serprog)
target_sources(pico_serprog PRIVATE main.c usb_descriptors.c)
target_link_libraries(pico_serprog PRIVATE pico_stdlib pico_unique_id hardware_spi tinyusb_device)
pico_add_extra_outputs(pico_serprog)
