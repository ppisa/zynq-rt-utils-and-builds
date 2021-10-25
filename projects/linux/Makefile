KERNEL_GIT ?= git://github.com/ppisa/linux-kernel.git
KERNEL_BRANCH ?= linux-5.10.y-rt-pi
KERNEL_SRC_DIR ?= linux-5.10
KERNEL_BUILD_DIR ?= build/arm/zynq

ifneq ($(wildcard /usr/src/linux-devel),)
KERNEL_GIT_REF ?= /usr/src/linux-devel
endif

.PHONY: all clone update build

all: clone update build

clone:
	if [ ! -e $(KERNEL_SRC_DIR) ] ; then \
	  git clone $(if $(KERNEL_GIT_REF),--reference=$(KERNEL_GIT_REF)) $(KERNEL_GIT) $(KERNEL_SRC_DIR) ; \
	else \
	  echo kernel already clonned in $(KERNEL_SRC_DIR) ; \
	fi
	( cd $(KERNEL_SRC_DIR) && \
	  git checkout $(KERNEL_BRANCH))

update: | clone
	( cd $(KERNEL_SRC_DIR) && \
	  git pull)

build: | update
	( cd $(KERNEL_BUILD_DIR) && \
	  make -j`nproc`)
	mkdir -p $(KERNEL_BUILD_DIR)-modules && \
	INSTALL_MOD_PATH="$$(cd $(KERNEL_BUILD_DIR)-modules && pwd)" && \
	( cd $(KERNEL_BUILD_DIR) && \
	  make INSTALL_MOD_PATH=$$INSTALL_MOD_PATH modules_install)
