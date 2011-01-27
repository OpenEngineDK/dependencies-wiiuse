IF (EXISTS ${WIIUSE_DEPS_SRC_DIR})
  SET(TARGET wiiuse)
  
  IF (CMAKE_BUILD_TYPE MATCHES debug)
    ADD_DEFINITIONS(-DWITH_WIIUSE_DEBUG)
  ENDIF (CMAKE_BUILD_TYPE MATCHES debug)
  

  # Create the extension library
  ADD_LIBRARY(${TARGET}
    ${WIIUSE_DEPS_SRC_DIR}/classic.c
    ${WIIUSE_DEPS_SRC_DIR}/dynamics.c
    ${WIIUSE_DEPS_SRC_DIR}/events.c
    ${WIIUSE_DEPS_SRC_DIR}/guitar_hero_3.c
    ${WIIUSE_DEPS_SRC_DIR}/io.c
    ${WIIUSE_DEPS_SRC_DIR}/io_nix.c
    ${WIIUSE_DEPS_SRC_DIR}/ir.c
    ${WIIUSE_DEPS_SRC_DIR}/nunchuk.c
    ${WIIUSE_DEPS_SRC_DIR}/wiiuse.c
    )
ENDIF (EXISTS ${WIIUSE_DEPS_SRC_DIR})
