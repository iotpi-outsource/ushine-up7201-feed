#
# Copyright (C) 2006-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=rtc-rx8010
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define KernelPackage/rtc-rx8010
  SUBMENU:=Other modules
  TITLE:=Driver for RTC Epson RX8010
  AUTOLOAD:=$(call AutoLoad,70,rtc-rx8010)
  FILES:=$(PKG_BUILD_DIR)/rtc-rx8010.ko
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Build/Compile
	$(MAKE) -C "$(LINUX_DIR)" \
		CROSS_COMPILE="$(TARGET_CROSS)" \
		ARCH="$(LINUX_KARCH)" \
		SUBDIRS="$(PKG_BUILD_DIR)" \
		EXTRA_CFLAGS="$(BUILDFLAGS)" \
		modules
endef

$(eval $(call KernelPackage,rtc-rx8010))
