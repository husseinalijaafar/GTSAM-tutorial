

find_package(GTSAM REQUIRED)
  if(GTSAM_FOUND)
    message(STATUS "GTSAM Found")
 include_directories(${GTSAM_INCLUDE_DIR})
link_directories(${GTSAM_LIBRARY_DIRS})
add_executable(SimpleRotation_src SimpleRotation.cpp)
add_executable(robotMotion_src robotMotion.cpp)
add_executable(robotLocalization_src robotLocalization.cpp)

target_link_libraries(SimpleRotation_src gtsam)
target_link_libraries(robotMotion_src gtsam)
target_link_libraries(robotLocalization_src gtsam)


  else()
    message(WARNING "GTSAM is NOT found. GTSAM will not be used")
  endif()
message(STATUS "  GTSAM include dir      Yes (${GTSAM_INCLUDE_DIR})")
message(STATUS "  GTSAM library dir        Yes (${GTSAM_LIBRARY_DIRS})")
