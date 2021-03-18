cmake_minimum_required(VERSION 3.5 FATAL_ERROR)

project(httpserver LANGUAGES CXX)


message("${CMAKE_BINARY_DIR}")

# find_package(spdlog)




set_property(DIRECTORY PROPERTY EP_BASE ${CMAKE_BINARY_DIR}/subprojects)
set(STAGED_INSTALL_PREFIX ${CMAKE_BINARY_DIR}/stage)

add_subdirectory(external)

include(ExternalProject)
# ExternalProject_Add(spdlog
#     PREFIX spdlog
#     SOURCE_DIR ${PROJECT_SOURCE_DIR}/external/spdlog/spdlog-1.8.2
#     INSTALL_COMMAND
#       ""

# )