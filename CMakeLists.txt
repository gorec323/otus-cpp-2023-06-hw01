cmake_minimum_required(VERSION 3.5)

project(helloworld VERSION 0.0.1 LANGUAGES CXX)

configure_file(
    version.h.in
    ${CMAKE_BINARY_DIR}/version.h
)

if (NOT CMAKE_CXX_STANDARD)
    set(CMAKE_CXX_STANDARD 14)
endif()

set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(${PROJECT_NAME} main.cpp)

target_include_directories(${PROJECT_NAME}
PRIVATE
    ${CMAKE_BINARY_DIR}
)
