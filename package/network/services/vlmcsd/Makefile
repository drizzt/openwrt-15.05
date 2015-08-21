#
# Copyright (C) 2015 Timothy Redaelli
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=vlmcsd
PKG_VERSION:=svn812
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/vancepym/vlmcsd.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=0c0b23a496ab9d556672fe61967fc90f52ed3464

include $(INCLUDE_DIR)/package.mk

define Package/vlmcsd
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Other Servers
  TITLE:=KMS server on OpenWRT
  URL:=http://forums.mydigitallife.info/threads/50234-Emulated-KMS-Servers-on-non-Windows-platforms
endef

define Package/vlmcsd/description
	A KMS server on OpenWRT
endef

define Package/vlmcsd/conffiles
#
endef

MAKE_VARS += FEATURES=most

define Package/vlmcsd/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) files/$(PKG_NAME).init $(1)/etc/init.d/$(PKG_NAME)
endef

$(eval $(call BuildPackage,vlmcsd))
