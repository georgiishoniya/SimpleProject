cmake_minimum_required(VERSION 3.14)
project(PrimeTest)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/9d43b27f7a873596496a2ea70721b3f9eb82df01.zip
)

set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

enable_testing()

add_executable(
  PrimeTest
  PrimeTest.cpp
)
target_link_libraries(
  PrimeTest
  GTest::gtest_main
)

target_link_libraries(
  PrimeTest 
  primelib
)

include(GoogleTest)
gtest_discover_tests(PrimeTest)