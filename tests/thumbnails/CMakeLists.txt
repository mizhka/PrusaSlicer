get_filename_component(_TEST_NAME ${CMAKE_CURRENT_LIST_DIR} NAME)

add_executable(${_TEST_NAME}_tests 
    ${_TEST_NAME}_tests_main.cpp
    test_thumbnails_input_string.cpp
    test_thumbnails_ini_string.cpp
)

target_link_libraries(${_TEST_NAME}_tests test_common libslic3r)
set_property(TARGET ${_TEST_NAME}_tests PROPERTY FOLDER "tests")

# catch_discover_tests(${_TEST_NAME}_tests TEST_PREFIX "${_TEST_NAME}: ")
add_test(${_TEST_NAME}_tests ${_TEST_NAME}_tests ${CATCH_EXTRA_ARGS})