cmake_minimum_required(VERSION 3.12)
include(pico_sdk_import.cmake)

set(projname "mpu6050")

project(${projname} C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pico_sdk_init()

#include(example_auto_set_url.cmake)

add_executable(${projname}
        main.cpp
        dht11-pico.h
        dht11-pico.cpp
        )

target_link_libraries(${projname} pico_stdlib hardware_i2c hardware_adc hardware_pwm hardware_timer)
pico_add_extra_outputs(${projname})

