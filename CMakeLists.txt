cmake_minimum_required(VERSION 2.8)
project(jact)

set(TEMP_CXX_FLAGS  ${CMAKE_CXX_FLAGS} )
set(CMAKE_CXX_FLAGS "-std=c++11 -O3 ${TEMP_CXX_FLAGS}")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -DDEBUG -Wall")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -Wall")

include_directories( ${CMAKE_SOURCE_DIR}/lib )
include_directories( ${CMAKE_SOURCE_DIR}/src )

#file( GLOB OPENDDS_LIBS
#)

add_library(source
	lib/test/test.cpp
)

add_executable(main src/main.cpp)
target_link_libraries(main source)
