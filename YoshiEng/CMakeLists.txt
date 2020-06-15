set (YOSHIENG_SOURCE_FILES
	dummy.cpp
)

add_library(YoshiEng STATIC ${YOSHIENG_SOURCE_FILES})
add_subdirectory(YoshiCore)
target_link_libraries(YoshiEng PUBLIC YoshiCore)
target_include_directories(YoshiEng PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_options(YoshiEng PRIVATE -W4 -WX)
set_target_properties(YoshiEng PROPERTIES
    CXX_STANDARD 11
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)

source_group(TREE "${CMAKE_CURRENT_SOURCE_DIR}" FILES ${YOSHIENG_SOURCE_FILES})