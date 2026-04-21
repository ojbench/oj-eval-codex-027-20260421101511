cmake_minimum_required(VERSION 3.10)
project(problem_027)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(code_bin src/main.cpp)
if (MSVC)
  target_compile_options(code_bin PRIVATE /W4)
else()
  target_compile_options(code_bin PRIVATE -O2 -pipe -static-libstdc++ -static-libgcc -Wall -Wextra -Wpedantic)
endif()

add_custom_target(code ALL
  COMMAND ${CMAKE_COMMAND} -E copy_if_different $<TARGET_FILE:code_bin> ${CMAKE_SOURCE_DIR}/code
  DEPENDS code_bin
  BYPRODUCTS ${CMAKE_SOURCE_DIR}/code
  COMMENT "Copying built binary to source-root code"
)
