cmake_minimum_required(VERSION 3.6)
project(capnproto-java)

set(CMAKE_CXX_STANDARD 11)

find_package(PkgConfig REQUIRED)
pkg_search_module(CAPNP REQUIRED capnp)

add_executable(capnpc-java compiler/src/main/cpp/capnpc-java.c++)
target_compile_options(capnpc-java PUBLIC ${CAPNP_CFLAGS_OTHER})
target_include_directories(capnpc-java PUBLIC ${CAPNP_INCLUDE_DIRS})
target_link_libraries(capnpc-java ${CAPNP_LIBRARIES})
