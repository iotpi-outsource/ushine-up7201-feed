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
  	+uci +ubus \
	+mtk-linkit-webui

  CATEGORY:=Base system
  DEFAULT:=y
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Package/inkit/install
	$(INSTALL_DIR) $(1)/bin
	
	$(CP) ./files/* $(1)
endef

$(eval $(call BuildPackage,ushine-fsk))
