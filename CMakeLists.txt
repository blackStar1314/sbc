cmake_minimum_required(VERSION 3.10)
project(sbc)

add_subdirectory(sbc)

option(ENABLE_EXAMPLES "Enable examples" OFF)
if(ENABLE_EXAMPLES)
    add_subdirectory(src)
endif()

