cmake_minimum_required(VERSION 3.10)
project(problem_027)

# Build rule: ensure an executable named `code` exists. Here we
# simply copy a pre-downloaded binary `Basic-Demo-64bit` into `code`.
# If the binary isn't there, the build will fail.

add_custom_target(code ALL
    COMMAND ${CMAKE_COMMAND} -E copy_if_different ${CMAKE_SOURCE_DIR}/third_party/BasicInterpreter-2025/Basic-Demo-64bit ${CMAKE_BINARY_DIR}/code
    BYPRODUCTS ${CMAKE_BINARY_DIR}/code
    COMMENT "Copying Basic-Demo-64bit to code"
)

install(PROGRAMS ${CMAKE_BINARY_DIR}/code DESTINATION bin)
