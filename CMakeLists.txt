# JKM 2015, CMake port of tclap

SET(TCLAP_VERSION_MAJOR    1)
SET(TCLAP_VERSION_MINOR    2)
SET(TCLAP_VERSION_RELEASE  1)

SET(TCLAP_VERSION "${TCLAP_VERSION_MAJOR}.${TCLAP_VERSION_MINOR}.${TCLAP_VERSION_RELEASE}")
MATH(EXPR TCLAP_VERSION_DECIMAL "${TCLAP_VERSION_MAJOR} * 10000 + ${TCLAP_VERSION_MINOR} * 100 + ${TCLAP_VERSION_RELEASE}")

PROJECT(tclap)

CMAKE_MINIMUM_REQUIRED(VERSION 2.8.7)

# include tclap headers (for building tests)

set(TCLAP_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include)

################################################################

message(STATUS "
################################################################
tclap Configuration Summary
################################################################

    https://github.com/0u812/tclap

    Configured on host $ENV{COMPUTERNAME} ${HOSTNAME}
      host OS                   ${CMAKE_SYSTEM_NAME}
      host architecture         ${CMAKE_SYSTEM_PROCESSOR}

    General flags:
      CC                        ${CMAKE_C_COMPILER}
      CXX                       ${CMAKE_CXX_COMPILER}
      CFLAGS                    ${CMAKE_C_FLAGS}
      CXXFLAGS                  ${CMAKE_CXX_FLAGS}
      LDFLAGS                   ${CMAKE_EXE_LINKER_FLAGS}

    Installation prefix:        ${CMAKE_INSTALL_PREFIX}
    "
)

add_subdirectory(include)
add_subdirectory(examples)
# add_subdirectory(docs)
# add_subdirectory(tests)