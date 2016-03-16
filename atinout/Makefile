#
# Copyright (c) 2016 Adrian Guenter
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=atinout
PKG_VERSION:=0.9.1
PKG_RELEASE:=3
PKG_LICENSE:=GPL-3.0
PKG_LICENSE_FILE:=gplv3.txt

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/$(PKG_NAME)
PKG_MD5SUM:=4448694147cd630dde1abfd73a10d753

include $(INCLUDE_DIR)/package.mk

define Package/atinout
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=Telephony
  TITLE:=Send AT commands to a modem
  URL:=http://atinout.sourceforge.net/
  MAINTAINER:=Adrian Guenter <a@gntr.me>
  DEPENDS:=
endef

define Package/atinout/description
 Atinout is a program that reads a list of AT commands. It sends those 
 commands one by one to the modem, waiting for the final result code for 
 the currently executing command before continuing with the next command 
 in the list. The output from the commands is captured.
endef

CONFIGURE_VARS += \
  CC="$(TARGET_CC)" \
  CXX="$(TARGET_CC) +.c++" \
  CFLAGS="$(TARGET_CFLAGS) -Wall -DVERSION=\"\\\"$(PKG_VERSION)\\\"\"" \
  LDFLAGS="$(TARGET_LDFLAGS)"

define Build/Configure
	$(call Build/Configure/Default,--with-linux-headers=$(LINUX_DIR))
endef

define Build/Compile
	@echo -e "\n=== Build/Compile ==="
	$(CONFIGURE_VARS) $(MAKE) -C $(PKG_BUILD_DIR) \
		all \
		
endef

define Package/atinout/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/atinout $(1)/opt/bin/
endef

$(eval $(call BuildPackage,atinout))
