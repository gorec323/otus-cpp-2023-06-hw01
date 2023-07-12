cmake_minimum_required(VERSION 3.5)

set(PATCH_VERSION 1 CACHE INTERNAL "Patch version. Default = 1")
set(PROJECT_VERSION 0.0.${PATCH_VERSION} CACHE INTERNAL "Application version" FORCE)

project(helloworld_cli VERSION ${PROJECT_VERSION} LANGUAGES CXX)

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
