cmake_minimum_required(VERSION 3.14)
project(Linenoise C)

add_library(linenoise
	linenoise.c
	stringbuf.c
	utf8.c
)

target_include_directories(linenoise
	PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
)

add_executable(linenoise_example example.c)
target_link_libraries(linenoise_example linenoise)

add_executable(linenoise_utf8_example example.c)
target_link_libraries(linenoise_utf8_example linenoise)
target_compile_definitions(linenoise_utf8_example PUBLIC USE_UTF8)

