# Copyright (c) 2023 Nordic Semiconductor ASA
# SPDX-License-Identifier: Apache-2.0

add_subdirectory(${ZEPHYR_CURRENT_MODULE_DIR} cmsis)

if(CONFIG_CPU_CORTEX_M OR CONFIG_CPU_AARCH32_CORTEX_A OR CONFIG_CPU_AARCH32_CORTEX_R)
  zephyr_include_directories(.)
  # D605N sources still include CMSIS core headers directly, so expose the
  # external HAL module's core include path as well.
  zephyr_include_directories(${ZEPHYR_BASE}/../modules/hal/cmsis/CMSIS/Core/Include)
endif()
