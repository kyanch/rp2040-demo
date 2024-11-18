cmake_minimum_required(VERSION 3.13)

set(PICO_SDK_PATH ${CMAKE_CURRENT_SOURCE_DIR}/lib/pico-sdk)
set(PICO_BOARD pico2)

include(${CMAKE_CURRENT_SOURCE_DIR}/lib/pico-sdk/external/pico_sdk_import.cmake)

project(rp2040-demo VERSION 0.0.1)

pico_sdk_init()

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
# 遍历src下所有cpp文件
file(GLOB _SOURCES_ ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)
add_executable(main ${_SOURCES_})

# Add pico_stdlib library which aggregates commonly used features
target_link_libraries(main pico_stdlib)

# create map/bin/hex/uf2 file in addition to ELF.
pico_add_extra_outputs(main)

