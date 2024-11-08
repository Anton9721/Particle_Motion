cmake_minimum_required(VERSION 3.24)
project(ParticleMotion)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

include_directories("${PROJECT_SOURCE_DIR}/include")
file(GLOB CPP_SOURCES "source/*.cpp")

add_executable(ParticleMotion ${CPP_SOURCES} main.cpp)

find_package(OpenMP REQUIRED)
if(OpenMP_CXX_FOUND)
    target_link_libraries(ParticleMotion PUBLIC OpenMP::OpenMP_CXX)
endif()
