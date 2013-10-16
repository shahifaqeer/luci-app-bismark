#
# Copyright (C) 2006-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-bismark-passive
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/luci-app-bismarkpassive
  SECTION:=luci
  CATEGORY:=LuCI
  DEFAULT:=y
  TITLE:=BISmark passive
  URL:=http://github.com/shahifaqeer/luci-app-bismark*
  SUBMENU:=1. Applications
  DEPENDS:=+lua +libuci-lua +libubus-lua
endef

define Package/luci-app-bismark-passive/description
  Allows installation of experiments manager separate from
  luci version dependency.
endef

define Build/Prepare
endef

define Build/Compile
endef

define Package/luci-app-bismark-experiments-manager/install
	$(call Package/luci/install/template,$$(1),applications/luci-$(1)
endef

$(eval $(call application,bismark-experiments-manager,Bismark experiments manager,+bismark-experiments-manager))
define Package/luci-app-bismark-experiments-manager/postinst
#!/bin/sh
rm -f /tmp/luci-indexcache 
endef
define Package/luci-app-bismark-experiments-manager/prerm 
#!/bin/sh
rm -f /tmp/luci-indexcache
endef

#TODO add build/make methods
#TODO check eval, call
#TODO check dependencies
