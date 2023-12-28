include_directories(${PROJECT_SOURCE_DIR}/include/)

add_executable(HIDHopper-firmware main.cpp)

target_link_libraries(HIDHopper-firmware QuokkADB)

pico_add_extra_outputs(HIDHopper-firmware)