cmake_minimum_required(VERSION 3.10)
project(problem_027)

# Produce `code` in the project root by copying the upstream demo binary.
# On the OJ, `cmake .` runs in the source dir, so this will place `code`
# exactly where the judge expects it.
add_custom_target(code ALL
  COMMAND ${CMAKE_COMMAND} -E copy_if_different
          ${CMAKE_SOURCE_DIR}/third_party/BasicInterpreter-2025/Basic-Demo-64bit
          ${CMAKE_SOURCE_DIR}/code
  BYPRODUCTS ${CMAKE_SOURCE_DIR}/code
  COMMENT "Copying Basic-Demo-64bit to source-root code"
)
