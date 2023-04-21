cmake_minimum_required(VERSION 3.2)

#find_package(Catch2 3 REQUIRED)
add_subdirectory(lib/Catch2)

# These tests can use the Catch2-provided main
add_executable(tests 
    ${CMAKE_SOURCE_DIR}/src/010-TestCase.cpp
    ${CMAKE_SOURCE_DIR}/src/020-TestCase-1.cpp
    ${CMAKE_SOURCE_DIR}/src/020-TestCase-2.cpp
    ${CMAKE_SOURCE_DIR}/src/030-Asn-Require-Check.cpp
)

target_link_libraries(tests PRIVATE Catch2::Catch2WithMain)

# These tests need their own main
#add_executable(custom-main-tests test.cpp test-main.cpp)
#target_link_libraries(custom-main-tests PRIVATE Catch2::Catch2)
