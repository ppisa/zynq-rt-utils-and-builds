# Automatically generated by /usr/src/linux-2.6.26.5/scripts/mkmakefile: don't edit

VERSION = 5
PATCHLEVEL = 10

#ARCH            = x86_64
#CROSS_COMPILE   = x86_64-linux-gnu-

ARCH            = arm
#CROSS_COMPILE  ?= arm-unknown-linux-gnu-
CROSS_COMPILE   = arm-linux-gnueabihf-
QTDIR = /usr/share/qt4

export QTDIR

lastword = $(word $(words $(1)),$(1))
makedir := $(dir $(call lastword,$(MAKEFILE_LIST)))

MAKEARGS := -C $(shell cd $(makedir) ; cd ../../../linux-5.10 ; pwd )
MAKEARGS += O=$(if $(patsubst /%,,$(makedir)),$(CURDIR)/)$(patsubst .,,$(patsubst %/,%,$(makedir)))
MAKEARGS += ARCH=$(ARCH) $(if $(CROSS_COMPILE),CROSS_COMPILE=$(CROSS_COMPILE))
MAKEARGS += QTDIR=$(QTDIR)
MAKEARGS += W=1

MAKEFLAGS += --no-print-directory

.PHONY: all $(MAKECMDGOALS)

all	:= $(filter-out all Makefile,$(MAKECMDGOALS))

#$(warning makedir=$(makedir))
#$(warning MAKECMDGOALS=$(MAKECMDGOALS))
#$(warning MAKEARGS=$(MAKEARGS))
#$(error stop)

all:
	$(MAKE) $(MAKEARGS) $(all)

Makefile:;

$(all) %/: all
	@:

