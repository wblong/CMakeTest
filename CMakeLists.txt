cmake_minimum_required(VERSION 3.3)

project(foolib)

#输出目录

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/bin)

#是否开启测试
option(BUILD_TESTING "Build the testing tree." ON)

if(BUILD_TESTING)
	enable_testing()
endif()

add_subdirectory(foo)
add_subdirectory(app)