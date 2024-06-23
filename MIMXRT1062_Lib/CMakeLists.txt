add_library(
    MIMXRT1062_LIB STATIC
    "src/public/system_MIMXRT1062.c"

    "src/private/startup_mimxrt1062.cpp"
    "src/private/fsl_flexspi_nor_boot.c"
    "src/private/evkmimxrt1060_flexspi_nor_config.c"
)

set_property(GLOBAL PROPERTY MIMXRT1062_LINKER_FILE ${CMAKE_CURRENT_SOURCE_DIR}/linker/MIMXRT1062.ld)

target_include_directories(MIMXRT1062_LIB PUBLIC include/public PRIVATE include/private)

target_link_directories(MIMXRT1062_LIB PUBLIC linker)

target_link_libraries(MIMXRT1062_LIB CMSIS)