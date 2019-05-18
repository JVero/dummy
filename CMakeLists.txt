cmake_minimum_required(VERSION 3.10.0)
project(dummy)

set (dummy_VERSION_MAJOR 1)
set (dummy_VERSION_MINOR 0)

# configure a header file to pass some of the CMake settings
# to the source code
configure_file (
  "${PROJECT_SOURCE_DIR}/dummy.h.in"
  "${PROJECT_BINARY_DIR}/dummy.h"
  )

# add the binary tree to the search path for include files
# so that we will find dummyConfig.h
include_directories("${PROJECT_BINARY_DIR}")

add_executable(dummyprinter dummyprinter.cpp)

# add the install targets
# install (TARGETS dummy DESTINATION bin)
# install (FILES "${PROJECT_BINARY_DIR}/TutorialConfig.h"
         # DESTINATION include)
