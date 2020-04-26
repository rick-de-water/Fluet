# Create library
add_library(fluet INTERFACE)

# Add dependencies
target_include_directories(fluet INTERFACE  
	"$<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/..>"
	"$<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}/..>"
	"$<INSTALL_INTERFACE:include>"
)

# Add sources
set(FLUET_HEADERS)

# Create IDE project
add_custom_target(fluet_ide SOURCES ${FLUET_HEADERS})
set_target_properties(fluet_ide PROPERTIES FOLDER Libraries)
source_group(TREE "${CMAKE_CURRENT_SOURCE_DIR}" FILES ${FLUET_HEADERS})