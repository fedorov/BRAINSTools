## TESTING EX.
## [BRAINSTools_Build_Dir]/bin/testRandomForest [correct_dir]/optdigits.train [correct_dir]/optdigits.test [output_dir]/optdigitsTrainedModel.txt
add_executable(testRandomForest testRandomForest.cxx)
target_link_libraries(testRandomForest ${ITK_LIBRARIES} ${OpenCV_LIBRARIES})

ExternalData_add_test( ${PROJECT_NAME}FetchData NAME OpenCVRandomForestTest
  COMMAND ${LAUNCH_EXE} $<TARGET_FILE:testRandomForest>
  DATA{${TestData_DIR}/optdigits.train}
  DATA{${TestData_DIR}/optdigits.test}
  ${CMAKE_CURRENT_BINARY_DIR}/optdigitTrainedModel.output )
