cmake_minimum_required(VERSION 3.10)
project(sbc)

if(MSVC)
   # release生成pdb
   add_compile_options($<$<NOT:$<CONFIG:DEBUG>>:/Zi>)
   add_link_options($<$<NOT:$<CONFIG:DEBUG>>:/DEBUG>)
   add_link_options($<$<NOT:$<CONFIG:DEBUG>>:/OPT:REF>)
   add_link_options($<$<NOT:$<CONFIG:DEBUG>>:/OPT:ICF>)
endif()


add_subdirectory(sbc)

option(ENABLE_EXAMPLES "Enable examples" OFF)
if(ENABLE_EXAMPLES)
    add_subdirectory(src)
endif()

