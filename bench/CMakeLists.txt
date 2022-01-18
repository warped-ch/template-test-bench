cmake_minimum_required(VERSION 3.8)
project(TemplateBench CXX)

set(CMAKE_CXX_STANDARD 17)

include(FetchContent)

FetchContent_Declare(benchmark
  GIT_REPOSITORY https://github.com/google/benchmark.git
  GIT_TAG main)
#  get rid of googletest dependency, do not build or run the benchmark tests
set(BENCHMARK_ENABLE_GTEST_TESTS OFF CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(benchmark)

add_executable(template_bench
  example_bench.cpp)

target_link_libraries(template_bench PRIVATE benchmark::benchmark_main)
