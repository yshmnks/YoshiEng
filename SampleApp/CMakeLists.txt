project(SampleApp LANGUAGES CXX)

set (SAMPLEAPP_SOURCE_FILES
	src/SampleApp.cpp
)

set (SAMPLEAPP_RESOURCE_FILES
)

add_executable(SampleApp ${SAMPLEAPP_SOURCE_FILES} ${SAMPLEAPP_RESOURCE_FILES})
target_include_directories(SampleApp PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/src)
target_link_libraries(SampleApp PUBLIC YoshiEng)
target_compile_options(SampleApp PRIVATE -W4 -WX)
set_target_properties(SampleApp PROPERTIES
	CXX_STANDARD 11
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)

source_group(TREE "${CMAKE_CURRENT_SOURCE_DIR}" FILES ${SAMPLEAPP_SOURCE_FILES} ${SAMPLEAPP_RESOURCE_FILES})
