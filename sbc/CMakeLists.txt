project(libsbc)

file(GLOB_RECURSE SRCS ${CMAKE_CURRENT_SOURCE_DIR}/*.h ${CMAKE_CURRENT_SOURCE_DIR}/*.c)
source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${SRCS})
add_definitions(-DSBC_DLL)
add_definitions(-DSBC_API_EXPORT)
add_library(${PROJECT_NAME} SHARED)
target_sources(${PROJECT_NAME} PRIVATE ${SRCS})
set_target_properties(${PROJECT_NAME} 
                        PROPERTIES 
                        OUTPUT_NAME 
                        ${PROJECT_NAME}$<$<CONFIG:DEBUG>:d>
                    )
set_target_properties(${PROJECT_NAME} 
                    PROPERTIES
                    PUBLIC_HEADER
                    ${CMAKE_CURRENT_SOURCE_DIR}/sbc.h
                    )

# install
install(TARGETS ${PROJECT_NAME}
        ARCHIVE DESTINATION lib  # lib
        RUNTIME DESTINATION bin  # dll
        PUBLIC_HEADER DESTINATION include/sbc # header
        )
install(FILES $<TARGET_PDB_FILE:${PROJECT_NAME}> DESTINATION bin OPTIONAL)