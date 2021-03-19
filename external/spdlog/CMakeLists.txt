find_package(spdlog)

if(SPDLOG_FOUDN)
    message("found")
else()
    message("not found")
    include(ExternalProject)
    EXternalProject_Add(spdlog
        URL
            /root/projects/httpserver/external/spdlog/spdlog-1.8.2.tar.gz
        BUILD_IN_SOURCE
            1
        CMAKE_ARGS
            # -DCMAKE_C_FLAGS:STRING=${CMAKE_C_FLAGS}
            -DCMAKE_INSTALL_PREFIX=${STAGED_INSTALL_PREFIX}
    )

  # set(
  #   SPDLOG_DIR ${STAGED_INSTALL_PREFIX}/${CMAKE_INSTALL_LIBDIR}/lib/cmake/spdlog
  #   CACHE PATH "Path to internally built FFTW3Config.cmake"
  #   FORCE
  #   )

  set(
    SPDLOG_ROOT ${STAGED_INSTALL_PREFIX}
    CACHE PATH "Path to internally built spdlog installation root"
    FORCE
    )
  set(
    SPDLOG_INCLUDEDIR ${SPDLOG_ROOT}/include
    CACHE PATH "Path to internally built spdlog include directories"
    FORCE
    )
  set(
    SPDLOG_LIBRARYDIR ${SPDLOG_ROOT}/lib
    CACHE PATH "Path to internally built spdlog library directories"
    FORCE
    )
endif()