cmake_minimum_required(VERSION 3.13)
# initialize the SDK based on PICO_SDK_PATH
# note: this must happen before project()
include(pico_sdk_import.cmake) # This must happen before project()

project(my_project)
pico_sdk_init()

#project(led_blink C CXX ASM)

#set(CMAKE_CXX_STANDARD 14)

#add_compile_options(-Wall
#        -Wno-format          # int != int32_t as far as the compiler is concerned because gcc has int32_t as long int
#        -Wno-unused-function # we have some for the docs that aren't called
#        -Wno-maybe-uninitialized
#        )

add_executable(led_blink main.cpp)
target_link_libraries(led_blink pico_stdlib)

# create map/bin/hex/uf2 file etc.
pico_add_extra_outputs(led_blink)
