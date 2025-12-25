include(CTest)
enable_testing()

add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/vendor/googletest)

# 临时的测试，用于打通测试逻辑
add_executable(tHelloWorld tHelloWorld.cpp)
target_link_libraries(tHelloWorld PRIVATE ${TARGET_NAME} gtest_main)
add_test(NAME tHelloWorld COMMAND tHelloWorld)
