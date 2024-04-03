cmake_minimum_required(VERSION 3.7)
project(Filters)

include(filters.cmake)

add_definitions(-fpic)

SET(LIBA52_SRC
        ${CMAKE_SOURCE_DIR}/dec_ac52.c
        ${CMAKE_SOURCE_DIR}/reframe_ac3.c
        ${CMAKE_SOURCE_DIR}/av_parsers.c
        ${CMAKE_SOURCE_DIR}/bitstream.c
        ${CMAKE_SOURCE_DIR}/descriptors.c
)

SET(LIBA52_LIB
        ${CMAKE_SOURCE_DIR}/lib/liba52.a
)

SET(LIBA52_INCLUDE
        ${CMAKE_SOURCE_DIR}/include
)

add_filter(liba52
        "${LIBA52_SRC}"
        "${LIBA52_LIB}"
        []
        GPAC_HAS_LIBA52
        "${LIBA52_INCLUDE}"
        ""
        "1")