cmake_minimum_required(VERSION 3.10)

project(cpp_exam)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 构建可执行文件
add_executable(${PROJECT_NAME} main.cpp Song.cpp)

# 指定输出目录（防止评分系统找不到可执行文件）
set_target_properties(${PROJECT_NAME} PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}
)

enable_testing()

# 注册所有测试
add_test(NAME Test1_BasicAddList COMMAND ${PROJECT_NAME})
add_test(NAME Test2_DataValidation COMMAND ${PROJECT_NAME})
add_test(NAME Test3_SearchFunction COMMAND ${PROJECT_NAME})
add_test(NAME Test4_ModifyFunction COMMAND ${PROJECT_NAME})
add_test(NAME Test5_TagManagement COMMAND ${PROJECT_NAME})
add_test(NAME Test6_SortFunction COMMAND ${PROJECT_NAME})
add_test(NAME Test7_DeleteFunction COMMAND ${PROJECT_NAME})
add_test(NAME Test8_Comprehensive COMMAND ${PROJECT_NAME})

# 设置测试超时
set_tests_properties(
    Test1_BasicAddList
    Test2_DataValidation
    Test3_SearchFunction
    Test4_ModifyFunction
    Test5_TagManagement
    Test6_SortFunction
    Test7_DeleteFunction
    Test8_Comprehensive
    PROPERTIES TIMEOUT 10
)