zephyr_include_directories(include)

zephyr_library_sources(
  src/Clock_Ip_Cfg.c
)

# Definition of Trgmux_Ip_InstanceArr, referenced by the Trgmux driver; the
# headers it needs are only on the include path when the Mcl driver is built.
zephyr_library_sources_ifdef(CONFIG_QDEC_NXP_S32 src/Trgmux_Ip_Cfg.c)
