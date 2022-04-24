include(pico_sdk_import.cmake)
add_executable(pio_rotary_encoder pio_rotary_encoder.cpp)


pico_generate_pio_header(pio_rotary_encoder ${CMAKE_CURRENT_LIST_DIR}/pio_rotary_encoder.pio)

target_sources(pio_rotary_encoder PRIVATE pio_rotary_encoder.cpp)

target_link_libraries(pio_rotary_encoder PRIVATE
        pico_stdlib
        hardware_pio
        )

pico_add_extra_outputs(pio_rotary_encoder)

# enable usb output, disable uart output
pico_enable_stdio_usb(pio_rotary_encoder 1)
pico_enable_stdio_uart(pio_rotary_encoder 0)


