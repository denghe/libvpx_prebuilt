cmake_minimum_required(VERSION 3.20)

IF (WIN32)
	set(name libvpxgnu)
else()
	set(name vpxgnu)
endif ()
project(${name})

include_directories(
	./
)

set(SRCS)
file(GLOB_RECURSE SRCS
	*.c
	*.h
)

if (IOS)
	set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fembed-bitcode")
	set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -fembed-bitcode")
	set(CMAKE_OSX_ARCHITECTURES "arm64")
#	set_xcode_property (${name} IPHONEOS_DEPLOYMENT_TARGET "13.0")
	add_library(${name} STATIC ${SRCS})
else ()
	set(CMAKE_OSX_ARCHITECTURES "arm64;x86_64")
	add_library(${name} ${SRCS})
endif ()

