include(FetchContent)

FetchContent_Declare(
    libqemu
    GIT_REPOSITORY https://github.com/quic/qemu.git
    GIT_TAG libqemu-v9.1-v0.10
    GIT_SUBMODULES CMakeLists.txt
    GIT_SHALLOW TRUE
)
FetchContent_MakeAvailable(libqemu)

set(LIBQEMU_CXX_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/include/libqemu-cxx)

add_library(libqemu-cxx
    libqemu-cxx.cc
    ${LIBQEMU_CXX_INCLUDE_DIR}/libqemu-cxx.h
)

#target_include_directories(libqemu-cxx PUBLIC ${PROJECT_SOURCE_DIR}/include)
