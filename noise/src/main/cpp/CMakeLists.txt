cmake_minimum_required(VERSION 3.4.1)

add_library(noise
        SHARED
        "${CMAKE_SOURCE_DIR}/noise.c"
        "${CMAKE_SOURCE_DIR}/kissfft/kiss_fft.c"
        "${CMAKE_SOURCE_DIR}/kissfft/tools/kiss_fftr.c")

target_include_directories(noise
        PRIVATE
        "${CMAKE_SOURCE_DIR}/kissfft"
        "${CMAKE_SOURCE_DIR}/kissfft/tools")

find_library(log-lib
        log)

target_link_libraries(noise
        ${log-lib})