# SPDX-FileCopyrightText: Copyright (c) 2022 Sidings Media 
# SPDX-License-Identifier: MIT

cmake_minimum_required(VERSION 3.22)

set(CMAKE_TRY_COMPILE_TARGET_TYPE "STATIC_LIBRARY")

project("SMRC-bootloader" C CXX ASM)

add_subdirectory(rp2040)
# add_subdirectory(esp32)