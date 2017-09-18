cmake_minimum_required(VERSION 3.0)

include_directories(deps/hiredis)
include_directories(deps/linenoise)
include_directories(deps/lua/src)
include_directories(deps/jemalloc/include)

add_compile_options(
  -std=c99
  -pedantic
  -Wall
  -W
  -Wno-missing-field-initializers
  -O0
  -g
  -ggdb
  -DUSE_JEMALLOC
)

link_libraries(/usr/local/lib/libjemalloc.a)

if(APPLE)
  link_libraries(${CMAKE_SOURCE_DIR}/deps/lua/src/liblua.a)
else()
  add_compile_options(-rdynamic)
  link_libraries(lua)
endif()

link_libraries(hiredis pthread dl m)

add_subdirectory(src)
