cmake_minimum_required(VERSION 3.4.1)

find_library( log-lib log )

set(libs_DIR src/main/jniLibs/${ANDROID_ABI})
set(libs_include_DIR src/main/cpp/opus/include)
include_directories(${libs_include_DIR})
link_directories(${libs_DIR})

add_library( opusJni SHARED src/main/cpp/opus-lib.cpp)
target_link_libraries( opusJni opus ${log-lib} )
