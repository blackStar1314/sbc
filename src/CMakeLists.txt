project(examples)

add_definitions(-D_CRT_SECURE_NO_WARNINGS)
include_directories(${CMAKE_SOURCE_DIR})
link_directories(${CMAKE_BINARY_DIR}/sbc)

add_executable(sbcdec sbcdec.c formats.h)
target_link_libraries(sbcdec PRIVATE libsbc)
add_executable(sbcenc sbcenc.c formats.h)
target_link_libraries(sbcenc PRIVATE libsbc)
add_executable(sbcinfo sbcinfo.c formats.h)
target_link_libraries(sbcinfo PRIVATE libsbc)
add_executable(sbctester sbctester.c formats.h)
target_link_libraries(sbctester PRIVATE libsbc)