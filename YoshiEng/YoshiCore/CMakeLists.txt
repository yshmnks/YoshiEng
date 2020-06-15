project(YoshiCore LANGUAGES CXX)

set(YOSHICORE_SOURCE_FILES
    ysMath.cpp
    ysMath.h
    ysTypes.h
    )
    
add_library(YoshiCore STATIC ${YOSHICORE_SOURCE_FILES})
target_include_directories(YoshiCore PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_options(YoshiCore PRIVATE -W4 -WX)
set_target_properties(YoshiCore PROPERTIES
    CXX_STANDARD 11
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)

source_group(TREE "${CMAKE_CURRENT_SOURCE_DIR}" FILES ${YOSHICORE_SOURCE_FILES})