cmake_minimum_required(VERSION 3.0)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/tests)

# tdog Test Framework
file(GLOB TDOG_SOURCES src/* )
add_library(tdog ${TDOG_SOURCES})
if(BORLAND AND NOT ${CMAKE_CXX_COMPILER} MATCHES ".*bcc32c.*")
  target_compile_definitions(tdog PUBLIC TDOG_COUNTER_ID)
endif()
target_include_directories(tdog PUBLIC inc/)