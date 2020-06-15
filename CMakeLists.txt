cmake_minimum_required(VERSION 3.17)

project(YoshiEng LANGUAGES CXX)

set(CMAKE_CONFIGURATION_TYPES "Debug;RelWithDebInfo" CACHE STRING "" FORCE)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/../bin)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/../bin)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/../bin)

add_subdirectory(YoshiEng)

option(BUILD_SAMPLEAPP "Build the YoshiEng SampleApp" ON)

if (BUILD_SAMPLEAPP)
	add_subdirectory(SampleApp)
	# default startup project for Visual Studio
	if (MSVC)
		set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT SampleApp)
		set_property(TARGET SampleApp PROPERTY VS_DEBUGGER_WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}/SampleApp")
	endif()
endif()
