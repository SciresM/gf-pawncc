#build file for CMake, see http://www.cmake.org/

CMAKE_MINIMUM_REQUIRED(VERSION 2.4)
PROJECT(gf-pawncc)

set(PAWN_CELL_SIZE "32bit" CACHE STRING "The cell size of the target abstract machine. This should correspond to the target platform's architecture.")
set_property(CACHE PAWN_CELL_SIZE PROPERTY STRINGS 32bit 64bit)

if (PAWN_CELL_SIZE STREQUAL 64bit)
	add_definitions(-DPAWN_CELL_SIZE=64)
endif()

ADD_SUBDIRECTORY(./compiler)
