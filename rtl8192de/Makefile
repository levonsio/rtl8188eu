
CC = gcc
KVER  := $(shell uname -r)
KSRC := /lib/modules/$(KVER)/build
MODDESTDIR := /lib/modules/$(KVER)/kernel/drivers/net/wireless/
PWD := $(shell pwd)

EXTRA_CFLAGS += -O2

ccflags-y += -D__CHECK_ENDIAN__

####################################################
obj-m := rtl8192de.o


PCI_92DE_HAL_OBJS:=	\
	dm.o		\
	fw.o		\
	hw.o		\
	led.o		\
	phy.o		\
	rf.o		\
	sw.o		\
	table.o		\
	trx.o		\

####################################################

rtl8192de-objs += $(PCI_92DE_HAL_OBJS)

default:
	        $(MAKE) -C $(KSRC) M=$(PWD) modules

.PHONY:clean
clean:
	rm -fr *.mod.c *.mod *.o .*.cmd *.ko *~
	rm -fr .tmp_versions
	rm -fr Modules.symvers
	rm -fr Module.symvers
	rm -fr Module.markers
	rm -fr modules.order
	rm -fr tags

