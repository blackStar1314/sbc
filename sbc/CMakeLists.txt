project(libsbc)

file(GLOB_RECURSE SRCS ${CMAKE_CURRENT_SOURCE_DIR}/*.h ${CMAKE_CURRENT_SOURCE_DIR}/*.c)
source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${SRCS})
add_definitions(-DSBC_DLL)
add_definitions(-DSBC_API_EXPORT)
add_library(${PROJECT_NAME} SHARED)
target_sources(${PROJECT_NAME} PRIVATE ${SRCS})