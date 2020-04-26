cmake_minimum_required(VERSION 3.12)

# Create project
project(fluet)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

# Set install prefix
if(CMAKE_INSTALL_PREFIX_INITIALIZED_TO_DEFAULT)
	set(CMAKE_INSTALL_PREFIX "${CMAKE_SOURCE_DIR}/install" CACHE PATH "Installation path" FORCE)
endif()

# Set options
set(FLUET_TEST_CXX_VERSION 11 CACHE STRING "The version of C++ to test with")
option(FLUET_WARNINGS_AS_ERRORS "Treat warnings as errors" OFF)
option(FLUET_SANITIZE "Run santizers" OFF)
option(FLUET_COVERAGE "Run code coverage analysis" OFF)

# Add subdirectories
add_subdirectory(src)