cmake_minimum_required(VERSION 3.20)

set(name libvpxgnu)
project(${name})

include_directories(
	./
)

set(SRCS)
file(GLOB_RECURSE SRCS
	*.c
	*.h
)
add_library(${name} ${SRCS})
