
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# TODO: add config sample file to package?

include $(TOPDIR)/rules.mk

PKG_NAME:=simpleproxy
PKG_VERSION:=3.5
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/vzaliva/simpleproxy.git
PKG_SOURCE_DATE:=2016-09-06
PKG_SOURCE_VERSION:=2328a3c2265eb3363bcc45a02f1d1455023a468f
#PKG_MIRROR_HASH:=8a82b18c3d0b16ae467d504cb9ad13e8bc7bd3318dc5f33bfe5ad82738fd858a

PKG_MAINTAINER:=Thomas Kupper <thomas.kupper@gmail.com>
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=LICENSE-GPL2

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/simpleproxy
  SECTION:=simpleproxy
  CATEGORY:=Network
  URL:=https://github.com/vzaliva/simpleproxy
  TITLE:=Simple TCP proxy
endef

define Package/simpleproxy/description
  Simple TCP/IP proxy. Also provides simple POP3 pre-auth.
  Can use HTTPs proxy to traverse firewalls.
endef

define Package/simpleproxy/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_DIR) $(1)/opt/share/man/man1
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/bin/simpleproxy $(1)/opt/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/man/man1/simpleproxy.1 $(1)/opt/share/man/man1/
endef

$(eval $(call BuildPackage,simpleproxy))
