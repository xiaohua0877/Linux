ROOTFS_DIR=/opt/4412/rootfs

MODULE_NAME = simple_input
APP_NAME = simple_input_test

CROSS_COMPILE = /home/george/Linux/toolchain/gcc-4.64/bin/arm-none-linux-gnueabi-

cc = $(CROSS_COMPILE)gcc

ifeq ($(KERNELRELEASE),)

KERNEL_DIR = /home/george/LINUX_4412/kernel/linux-3.14
CUR_DIR = $(shell pwd)

all:
    make -C $(KERNEL_DIR)  M=$(CUR_DIR) modules
    
    
clean:
    make -C $(KERNEL_DIR)  M=$(CUR_DIR) clean
    rm -rf $(APP_NAME)

install:
    cp -raf *.ko  $(APP_NAME)  $(ROOTFS_DIR)/drv_module

else

obj-m  += $(MODULE_NAME).obj

