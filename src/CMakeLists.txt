cmake_minimum_required(VERSION 3.5)

project(httpserver LANGUAGES CXX)
message("=============================================================================")
# find_package(spdlog PATHS /root/projects/httpserver/build/stage/lib/cmake/spdlog)
find_package(spdlog REQUIRED)
message("${CMAKE_PREFIX_PATH}  yes yes eys")
if (spdlog_FOUND) 
    message("=============>yes")
else()
    message("+++++++++++++++++no!!")
endif() 

add_executable(httpserver main.cpp)

target_link_libraries(httpserver
    PUBLIC
        spdlog
)
