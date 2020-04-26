# Create executable
add_executable(test_fluet)
set_target_properties(test_fluet PROPERTIES FOLDER Tests)

# Add dependencies
target_link_libraries(test_fluet test_main fluet)
target_include_directories(test_fluet PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/..")

# Add sources
set(TEST_FLUET_SOURCES)

list(APPEND TEST_FLUET_SOURCES "test.cpp")

# Create source groups
target_sources(test_fluet PRIVATE ${TEST_FLUET_SOURCES})
source_group(TREE "${CMAKE_CURRENT_SOURCE_DIR}" FILES ${TEST_FLUET_SOURCES})

# Add target as tests
add_test(NAME fluet COMMAND test_fluet)