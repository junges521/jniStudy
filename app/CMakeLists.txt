CMake_minimum_required(VERSION 3.4.1)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/src/main/jniLibs/${ANDROID_ABI})

# 头文件路径
include_directories(src/main/cpp/)

add_library( hook SHARED src/main/cpp/JniLib.c)

find_library(log-lib log)

target_link_libraries( hook ${log-lib} )