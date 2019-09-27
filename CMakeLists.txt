cmake_minimum_required(VERSION 2.6.4)
project(LIBNMEA C)

include_directories(include)

# The shared OSAL and cFE include directories should always be used
# Note that this intentionally does NOT include PSP-specific includes, just the generic
include_directories(${CFECORE_SOURCE_DIR}/src/inc)
include_directories(${CFEPSP_SOURCE_DIR}/fsw/inc)

aux_source_directory(src LIB_SRC_FILES)

# Create the app module
add_cfe_app(libnmea ${LIB_SRC_FILES})

