#
# Copyright (c) 2016 Adrian Guenter
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=efax
PKG_MAINTAINER:=Adrian Guenter <a@gntr.me>

PKG_VERSION:=0.9a-001114
PKG_MD5SUM:=9b7dc52656f5cbec846a7ba3299f73bd
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://www.cce.com/efax/download/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz

include $(INCLUDE_DIR)/package.mk

define Package/efax
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=Telephony
  URL:=https://www.cce.com/efax/
  TITLE:=efax
  DEPENDS:=
endef

define Package/hylafax/description
 A small ANSI C/POSIX program which sends and receives 
 faxes using any fax modem (Class 1, 2 or 2.0).
endef



define Build/Configure
	$(call Build/Configure/Default,--with-linux-headers=$(LINUX_DIR))
endef

define Package/efax/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/{efax,efix,fax} $(1)/opt/bin/
endef

$(eval $(call BuildPackage,efax))
