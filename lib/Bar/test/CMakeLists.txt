cmake_minimum_required(VERSION 3.1.0)

project(${PARENT_PROJECT_NAME}_test)

include(CTest)
enable_testing()

add_executable(${PARENT_PROJECT_NAME}_test ${PARENT_PROJECT_NAME}_test.cpp)

include_directories(${GTEST_INCLUDE_DIRS})

target_link_libraries(${PARENT_PROJECT_NAME}_test ${PARENT_PROJECT_NAME} CONAN_PKG::gtest)

gtest_discover_tests(${PARENT_PROJECT_NAME}_test)

target_include_directories(${PARENT_PROJECT_NAME}_test PUBLIC
    ${CMAKE_SOURCE_DIR}/${PARENT_PROJECT_NAME}/include
)