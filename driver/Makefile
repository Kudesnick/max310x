obj-m += max310x.o

KERNELDIR ?= /lib/modules/$(shell uname -r)

all max310x.ko:
	make -C $(KERNELDIR)/build M=$(PWD) modules

clean:
	make -C $(KERNELDIR)/build M=$(PWD) clean

install: max310x.ko
	xz -c max310x.ko > $(KERNELDIR)/kernel/drivers/tty/serial/max310x.ko.xz

reload:
	rmmod max310x && modprobe max310x
