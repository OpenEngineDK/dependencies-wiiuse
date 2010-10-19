SET(TARGET Externals_Wiiuse)

SET(SRC_ROOT
  wiiuse_v0.12/src#/release-i486-linux-gnu
  )

FIND_PATH(WIIUSE_INCLUDE_DIR NAMES wiiuse.h
  PATHS
  ${SRC_ROOT}
)


# Create the extension library
ADD_LIBRARY(${TARGET}
  ${SRC_ROOT}/classic.c
  ${SRC_ROOT}/dynamics.c
  ${SRC_ROOT}/events.c
  ${SRC_ROOT}/guitar_hero_3.c
  ${SRC_ROOT}/io.c
  ${SRC_ROOT}/io_nix.c
  ${SRC_ROOT}/ir.c
  ${SRC_ROOT}/nunchuk.c
  ${SRC_ROOT}/wiiuse.c
)

# ADD_CUSTOM_COMMAND(
#   TARGET ${TARGET}
#   PRE_BUILD
#   COMMAND make ARGS "-C wiiuse_v0.12"
#   )
