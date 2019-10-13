cmake_minimum_required (VERSION 2.6)
project (leptjson_test C)

set(**DCMAKE_BUILD_TYPE**** debug**)
IF(NOT DCMAKE_BUILD_TYPE)
    SET(DCMAKE_BUILD_TYPE Release)
ENDIF()
MESSAGE("Build type: " ${DCMAKE_BUILD_TYPE})

if (CMAKE_C_COMPILER_ID MATCHES "GNU|Clang")
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -ansi -pedantic -Wall")
endif()

add_library(leptjson leptjson.c)
add_executable(leptjson_test test.c)
target_link_libraries(leptjson_test leptjson)
