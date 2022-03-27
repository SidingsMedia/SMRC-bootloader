# SPDX-FileCopyrightText: Copyright (c) 2022 Sidings Media 
# SPDX-License-Identifier: MIT

cmake_minimum_required(VERSION 3.22)

include(pico-sdk/pico_sdk_init.cmake)
include(cmake/sourcelist.cmake)

# project(SMRC-rp2040-bootloader C CXX ASM)

set(VERSION_MAJOR "1")
set(VERSION_MINOR "0")
set(VERSION_PATCH "0")
set(VERSION ${VERSION_MAJOR}.${VERSION_MINOR}.${VERSION_PATCH})
set(EXE_NAME smrc-bootloader-rp2040-${VERSION})
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 11)

pico_sdk_init()

add_executable(rp2040 ${SRC_LIST})

pico_add_extra_outputs(rp2040)

target_link_libraries(rp2040 pico_stdlib)

add_compile_options(-Wall
        -Wno-format          # int != int32_t as far as the compiler is concerned because gcc has int32_t as long int
        -Wno-unused-function # we have some for the docs that aren't called
        -Wno-maybe-uninitialized
        )
