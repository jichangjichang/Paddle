file(GLOB TEST_OPS RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}" "test_*.py")
string(REPLACE ".py" "" TEST_OPS "${TEST_OPS}")

# default test
foreach(src ${TEST_OPS})
    if (NOT ${src} STREQUAL "test_recognize_digits")
        py_test (${src} SRCS ${src}.py)
    endif(NOT ${src} STREQUAL "test_recognize_digits")
endforeach()

add_subdirectory(high-level-api)
