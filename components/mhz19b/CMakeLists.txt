include($ENV{IDF_PATH}/tools/cmake/version.cmake)

if(${IDF_VERSION_MAJOR} STREQUAL 4 AND ${IDF_VERSION_MINOR} STREQUAL 1 AND ${IDF_VERSION_PATCH} STREQUAL 3)
  set(req log esp_idf_lib_helpers driver)
else()
  set(req log esp_idf_lib_helpers driver esp_timer)
endif()

idf_component_register(SRCS "mhz19b.c"
  INCLUDE_DIRS "."
  REQUIRES ${req})
