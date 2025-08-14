cmake_minimum_required(VERSION 3.5.1)

project(simple-library VERSION 1.0.0 LANGUAGES CXX)

# Build source files
add_subdirectory(src)

# Enable testing
enable_testing()
add_subdirectory(tests)

# Install headers
install(DIRECTORY ${CMAKE_SOURCE_DIR}/src/ 
        DESTINATION include/simple-library
        FILES_MATCHING PATTERN "*.h")

# Install library
install(TARGETS simple-library
        ARCHIVE DESTINATION lib
        LIBRARY DESTINATION lib
        RUNTIME DESTINATION bin)

