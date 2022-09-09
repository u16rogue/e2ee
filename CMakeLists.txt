cmake_minimum_required(VERSION 3.18)

add_subdirectory("deps/cryptopp-cmake")
add_subdirectory("libs/e2eelib")
add_subdirectory("deps/kita")

project(e2ee)

add_executable(
	${PROJECT_NAME}
	"src/main.cpp"
)

target_link_libraries(
	${PROJECT_NAME}
	PRIVATE
	cryptopp
	e2eelib
	kita
)