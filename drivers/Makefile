#
# Makefile for the Linux kernel device drivers.
#
# 15 Sep 2000, Christoph Hellwig <hch@infradead.org>
# Rewritten to use lists instead of if-statements.
#

obj-y				+= irqchip/
obj-y				+= bus/

obj-$(CONFIG_GENERIC_PHY)	+= phy/

# GPIO must come after pinctrl as gpios may need to mux pins etc
obj-$(CONFIG_PINCTRL)		+= pinctrl/
obj-$(CONFIG_GPIOLIB)		+= gpio/
obj-y				+= pwm/
obj-$(CONFIG_PARISC)		+= parisc/
obj-y				+= idle/

# IPMI must come before ACPI in order to provide IPMI opregion support
obj-y				+= char/ipmi/

# PnP must come after ACPI since it will eventually need to check if acpi
# was used and do nothing if so
obj-y				+= amba/

obj-y				+= clk/
# Many drivers will want to use DMA so this has to be made available
# really early.
obj-$(CONFIG_DMADEVICES)	+= dma/

# SOC specific infrastructure drivers.
obj-y				+= soc/

# regulators early, since some subsystems rely on them to initialize
obj-$(CONFIG_REGULATOR)		+= regulator/

# reset controllers early, since gpu drivers might rely on them to initialize

# tty/ comes before char/ so that the VT console is the boot-time
# default.
obj-y				+= tty/
obj-y				+= char/

# iommu/ comes before gpu as gpu are using iommu controllers

# gpu/ comes after char for AGP vs DRM startup and after iommu

# i810fb and intelfb depend on char/agp/

obj-y				+= base/ block/ misc/ mfd/
obj-$(CONFIG_DMA_SHARED_BUFFER) += dma-buf/
obj-$(CONFIG_NUBUS)		+= nubus/
obj-$(CONFIG_MTD)		+= mtd/
obj-$(CONFIG_SPI)		+= spi/
obj-y				+= net/
obj-$(CONFIG_FUSION)		+= message/
obj-$(CONFIG_DIO)		+= dio/
obj-$(CONFIG_SBUS)		+= sbus/
obj-$(CONFIG_ATA_OVER_ETH)	+= block/aoe/
obj-$(CONFIG_PARIDE) 		+= block/paride/
obj-$(CONFIG_TC)		+= tc/
obj-$(CONFIG_USB_PHY)		+= usb/
obj-$(CONFIG_USB)		+= usb/
obj-$(CONFIG_PCI)		+= usb/
obj-$(CONFIG_USB_GADGET)	+= usb/
obj-$(CONFIG_OF)		+= usb/
obj-$(CONFIG_SERIO)		+= input/serio/
obj-$(CONFIG_GAMEPORT)		+= input/gameport/
obj-$(CONFIG_INPUT)		+= input/
obj-$(CONFIG_RTC_LIB)		+= rtc/
obj-y				+= power/
obj-$(CONFIG_WATCHDOG)		+= watchdog/
obj-$(CONFIG_EISA)		+= eisa/
obj-y				+= lguest/
obj-$(CONFIG_CPU_FREQ)		+= cpufreq/
obj-$(CONFIG_CPU_IDLE)		+= cpuidle/
obj-$(CONFIG_NEW_LEDS)		+= leds/
obj-y				+= firmware/
obj-$(CONFIG_CRYPTO)		+= crypto/
ifndef CONFIG_ARCH_USES_GETTIMEOFFSET
obj-y				+= clocksource/
endif
obj-$(CONFIG_PPC_PS3)		+= ps3/
obj-$(CONFIG_OF)		+= of/
obj-$(CONFIG_VHOST_RING)	+= vhost/
obj-$(CONFIG_VHOST)		+= vhost/


# Virtualization drivers

obj-$(CONFIG_MEMORY)		+= memory/
obj-$(CONFIG_IIO)		+= iio/
