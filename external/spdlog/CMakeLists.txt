find_package(Spdlog)

if(Spdlog_FOUDN)
    message("found")
else()
    message("not found")
    include(ExternalProject)
    EXternalProject_Add(spdlog
        URL
            /root/projects/httpserver/external/spdlog/spdlog-1.8.2.tar.gz
        BUILD_IN_SOURCE
            1
        LOG_BUILD
            1
        CMAKE_ARGS
            # -DCMAKE_C_FLAGS:STRING=${CMAKE_C_FLAGS}
            -DCMAKE_INSTALL_PREFIX=${STAGED_INSTALL_PREFIX}
    )
endif()