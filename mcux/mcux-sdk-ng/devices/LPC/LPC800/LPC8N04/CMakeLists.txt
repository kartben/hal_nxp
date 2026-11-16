# Copyright 2024 NXP
# All rights reserved.
#
# SPDX-License-Identifier: BSD-3-Clause

#### device headers and system files (single-file header, no peripheral split)
if(CONFIG_MCUX_COMPONENT_device.CMSIS)
    mcux_add_source(SOURCES fsl_device_registers.h LPC8N04.h LPC8N04_features.h)
    mcux_add_include(INCLUDES .)
endif()

if(CONFIG_MCUX_COMPONENT_device.system)
    mcux_add_source(SOURCES system_LPC8N04.c system_LPC8N04.h)
    mcux_add_include(INCLUDES .)
endif()

#### device spepcific drivers
mcux_add_cmakelists(${SdkRootDirPath}/${device_root}/LPC/LPC800/LPC8N04/drivers)

#### LPC shared drivers/components/middlewares, project segments
include(${SdkRootDirPath}/devices/LPC/shared.cmake)
