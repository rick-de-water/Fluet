# Create library
add_library(test_main STATIC)
set_target_properties(test_main PROPERTIES FOLDER Tests)

# Add dependencies
target_link_libraries(test_main fluet)

# Add sources
target_sources(test_main PRIVATE "main.cpp")
source_group("" FILES "main.cpp")