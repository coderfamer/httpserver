cmake_minimum_required(VERSION 3.5 FATAL_ERROR)

project(httpserver LANGUAGES CXX)


set_property(DIRECTORY PROPERTY EP_BASE ${CMAKE_BINARY_DIR}/subprojects)
set(STAGED_INSTALL_PREFIX ${CMAKE_BINARY_DIR}/stage)

add_subdirectory(external)

include(ExternalProject)
ExternalProject_Add(httpserver
    DEPENDS 
        spdlog
    SOURCE_DIR 
        ${CMAKE_CURRENT_SOURCE_DIR}/src
    CMAKE_CACHE_ARGS
        -DCMAKE_CXX_FLAGS:STRING=${CMAKE_CXX_FLAGS}
        -DCMAKE_INCLUDE_PATH:PATH=${SPDLOG_INCLUDEDIR}
        -DCMAKE_LIBRARY_PATH:PATH=${SPDLOG_LIBRARYDIR}
  BUILD_ALWAYS
    1
  INSTALL_COMMAND
    ""
)

message("==================>${SPDLOG_INCLUDEDIR}")


