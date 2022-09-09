cmake_minimum_required(VERSION 3.18)

if (NOT TARGET cryptopp)
	message(FATAL_ERROR "cryptopp target is unavailable.")
endif()

project(e2eelib)

add_library(
	${PROJECT_NAME} STATIC

	"include/e2eelib/e2eelib.hpp"
	"src/e2eelib.cpp"
)

target_include_directories(
	${PROJECT_NAME}
	PUBLIC
	"include/"
)

set_target_properties(
	${PROJECT_NAME}
	PROPERTIES
	CXX_STANDARD 20
)

target_link_libraries(
	${PROJECT_NAME}
	PRIVATE
	cryptopp
)