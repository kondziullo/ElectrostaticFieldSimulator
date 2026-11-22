cmake_minimum_required(VERSION 3.16)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(ElectrostaticField
    src/FieldRenderer.cpp
    src/Charge.cpp
    src/Vector2D.cpp
)

target_include_directories(ElectrostaticField PRIVATE include)

if(MSVC)
    target_compile_options(ElectrostaticField PRIVATE /W4)
else()
    target_compile_options(ElectrostaticField PRIVATE -Wall -Wextra -Wpedantic)
endif()