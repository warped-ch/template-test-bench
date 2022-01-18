cmake_minimum_required(VERSION 3.8)
project(TemplateTest CXX)

set(CMAKE_CXX_STANDARD 17)

include(FetchContent)

FetchContent_Declare(googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG main)
# Prevent overriding the parent project's compiler/linker settings on Windows
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

enable_testing()

add_executable(template_test
  example_test.cpp)

target_link_libraries(template_test PRIVATE gtest_main)

include(GoogleTest)
gtest_discover_tests(template_test)
