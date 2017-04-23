# U-boot for MicroZed build - use zynq_microzed_config

UBOOT_SRC_DIR := $(shell cd ../.. ; pwd )/src/u-boot-xlnx
BUILD_DIR := $(CURDIR)
CROSS_COMPILE=arm-linux-gnueabihf-

#$(warning makedir=$(makedir) CURDIR=$(CURDIR))

.PHONY: all $(MAKECMDGOALS)

all	:= $(filter-out all Makefile,$(MAKECMDGOALS))

all:
	echo $(MAKE) -C $(UBOOT_SRC_DIR) O=$(BUILD_DIR) CROSS_COMPILE=$(CROSS_COMPILE) $(MAKEARGS) $(all)
	$(MAKE) -C $(UBOOT_SRC_DIR) O=$(BUILD_DIR) CROSS_COMPILE=$(CROSS_COMPILE) $(MAKEARGS) $(all)

Makefile:;

$(all) %/: all
	@:
