foreach(testname
	tracez_processor_test)
  add_executable(${testname} "${testname}.cc")
  target_link_libraries(
    ${testname} ${GTEST_BOTH_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT}
    opentelemetry_zpages)

  gtest_add_tests(
    TARGET ${testname}
    TEST_PREFIX ext.
    TEST_LIST ${testname})
endforeach()

