file(GLOB_RECURSE SOURCES_C *.c
ui/generated/custom/*.c
ui/generated/guider_customer_fonts/*.c
ui/generated/guider_fonts/*.c
ui/generated/images/*.c

)
file(GLOB_RECURSE SOURCES_CPP *.cpp)


set(include_dirs  
.
ui/custom 
ui/generated
ui/generated/guider_customer_fonts
ui/generated/guider_fonts
ui/generated/images

)



idf_component_register(
    SRCS ${SOURCES_C} ${SOURCES_CPP} 
    INCLUDE_DIRS   ${include_dirs}
    )

target_compile_definitions(${COMPONENT_LIB} PUBLIC "-DLV_HOR_RES_MAX=240")
target_compile_definitions(${COMPONENT_LIB} PUBLIC "-DLV_VER_RES_MAX=240")