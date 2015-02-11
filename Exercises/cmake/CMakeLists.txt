cmake_minimum_required(VERSION 2.8)
project(Exercises)

# Headers used by all exercises
include_directories(../Cpp_common)
set (COMMON_HEADERS
  ../Cpp_common/cl.hpp
  ../Cpp_common/device_picker.hpp
  ../Cpp_common/err_code.h
  ../Cpp_common/util.hpp
  ../Cpp_common/wtime.c
  )

# Utility to create a new exercise
macro(add_exercise name sources)
  add_executable(${ARGV} ${COMMON_HEADERS})
  target_link_libraries(${name} OpenCL)
endmacro(add_exercise)

# Create the exercises
add_exercise(
  Exercise01
  ../Exercise01/Cpp/DeviceInfo.cpp
)
add_exercise(
  Exercise04
  ../Exercise04/Cpp/vadd.cpp
)
add_exercise(
  Exercise06
  ../Exercise06/Cpp/matmul.cpp
  ../Exercise06/Cpp/matmul.hpp
  ../Exercise06/Cpp/matrix_lib.cpp
  ../Exercise06/Cpp/matrix_lib.hpp
)
