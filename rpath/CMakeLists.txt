cmake_minimum_required(VERSION 3.10)
project(lean-rpath)

add_library(foo foo.c)

add_library(bar bar.c)

add_library(foobar foobar.c)
target_link_libraries(foobar PRIVATE foo bar)

get_property(foobarDeps
	TARGET foobar
	PROPERTY LINK_LIBRARIES)
message(STATUS "${foobarDeps}")

add_executable(${PROJECT_NAME} main.c)
target_link_libraries(${PROJECT_NAME} PRIVATE foobar)
