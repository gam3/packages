#
# Copyright (C) 2016-2024 G. Allen Morris III
#
# This is free software, licensed under the Apache License, version 2.0
#

include $(TOPDIR)/rules.mk

PKG_NAME:=netwatch
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_MAINTAINER:=G. Allen Morris III <gam3@gam3.net>
PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/netwatch
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=+fping +busybox
  TITLE:=Monitor Network connection and control leds
  PKGARCH:=all
  PROVIDES:=netwatch-daemon
endef

define Package/netwatch/description
Monitor Network connection and control leds accordingly
endef

define Package/netwatch/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_BIN) ./sbin/netwatch $(1)/usr/sbin
	$(INSTALL_BIN) ./files/netwatch.init $(1)/etc/init.d/netwatch
	$(INSTALL_CONF) ./files/netwatch.config $(1)/etc/config/netwatch
endef


define Build/Configure
endef

define Build/Compile
endef

$(eval $(call BuildPackage,netwatch))
