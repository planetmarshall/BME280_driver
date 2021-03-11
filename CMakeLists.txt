cmake_minimum_required(VERSION 3.1)
project(bme280 VERSION 3.5.0 LANGUAGES C)

add_library(bme280 
	bme280.c
	bme280.h
	bme280_defs.h)

target_include_directories(bme280 PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

add_executable(bme280_example examples/linux_userspace.c)
target_link_libraries(bme280_example PRIVATE bme280)
