# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.

include $(TOPDIR)/rules.mk

PKG_NAME:=ushine-fsk
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/ushine-fsk
  TITLE:=Ushine UP7201 FSK
  HIDDEN:=1
  DEPENDS:=@TARGET_ramips_mt7688_LinkIt7688 \
  	+libuci +ubus +libcares +libmosquitto \
	+curl +libstdcpp +libmraa +libjson-c

  CATEGORY:=Base system
  DEFAULT:=y
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Compile
endef

define Package/ushine-fsk/install
	$(INSTALL_DIR) $(1)/bin
	
	$(CP) ./files/* $(1)
endef

$(eval $(call BuildPackage,ushine-fsk))
