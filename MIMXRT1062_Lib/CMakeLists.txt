add_library(
    MIMXRT1062_LIB STATIC
    "public/src/system_MIMXRT1062.c"

    "private/src/startup_mimxrt1062.cpp"
    "private/src/fsl_flexspi_nor_boot.c"
    "private/src/evkmimxrt1060_flexspi_nor_config.c"
)

set_property(GLOBAL PROPERTY MIMXRT1062_LINKER_FILE ${CMAKE_CURRENT_SOURCE_DIR}/linker/MIMXRT1062.ld)

target_include_directories(MIMXRT1062_LIB PUBLIC public/include PRIVATE private/include)

target_link_directories(MIMXRT1062_LIB PUBLIC linker)

target_link_libraries(MIMXRT1062_LIB CMSIS)