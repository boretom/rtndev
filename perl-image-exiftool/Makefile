#
# Copyright (C) 2015-2019 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=perl-image-exiftool
PKG_VERSION:=11.81
PKG_RELEASE:=1

PKG_SOURCE_URL:=http://www.sno.phy.queensu.ca/~phil/exiftool
PKG_SOURCE:=Image-ExifTool-$(PKG_VERSION).tar.gz
PKG_HASH:=6784b85230b430ef357f80f729db858f9edd7664253210944d426b84515e03c0

PKG_LICENSE:=GPL-1.0-or-later Artistic-1.0-Perl

PKG_BUILD_DIR:=$(BUILD_DIR)/perl/Image-ExifTool-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/perl/perlmod.mk

define Package/perl-image-exiftool
	SUBMENU:=Perl
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Perl library and command-line application for reading, writing and editing meta information
	URL:=https://www.sno.phy.queensu.ca/~phil/exiftool/
	DEPENDS:=+perl +perlbase-base +perlbase-encode +perlbase-essential +perlbase-file +perlbase-time
endef

define Build/Configure
	$(call perlmod/Configure,,)
endef

define Build/Compile
	$(call perlmod/Compile,,)
endef

define Package/perl-image-exiftool/install
	$(call perlmod/Install,$(1),File Image Image/ExifTool auto/Image/ExifTool)
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/bin/exiftool $(1)/opt/bin
	$(SED) 's,#!.*perl,#!/opt/bin/perl,' $(1)/opt/bin/exiftool

endef


$(eval $(call BuildPackage,perl-image-exiftool))
