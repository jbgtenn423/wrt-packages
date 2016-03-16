#
# Copyright (c) 2016 Adrian Guenter
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=efax
PKG_VERSION:=0.9a-001114
PKG_RELEASE:=2
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILE:=COPYING
PKG_MAINTAINER:=Adrian Guenter <a@gntr.me>

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://www.cce.com/efax/download/
PKG_MD5SUM:=9b7dc52656f5cbec846a7ba3299f73bd

include $(INCLUDE_DIR)/package.mk

define Package/efax
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=Telephony
  URL:=https://www.cce.com/efax/
  TITLE:=Small bidirectional fax utility
  DEPENDS:=
endef

define Package/efax/description
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
