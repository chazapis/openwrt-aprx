#
# Copyright (C) 2016 Antony Chazapis <chazapis@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=aprx
PKG_VERSION:=2.9.0
PKG_RELEASE:=1
PKG_LICENSE:=BSD-3-Clause

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://thelifeofkenneth.com/aprx/release
PKG_MD5SUM:=9a69509ceb67e2914743621ec3e5b876

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/aprx
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=+libpthread
  TITLE:=Hamradio APRS iGate / Digipeater
  URL:=http://thelifeofkenneth.com/aprx/
  MAINTAINER:=Antony Chazapis <chazapis@gmail.com>
endef

define Package/aprx/description
  Aprx is an APRS iGate that has minimal system requirements. It can handle
  an arbitrary number of radio modems, optionally relay APRS packets from radio
  to the APRS-IS network, optionally digipeat AX25 with or without NEWn-N
  rules, optionally relay APRS packets from APRS-IS to radio (TX-iGate)
endef

define Package/aprx/conffiles
/etc/aprx.conf
endef

define Build/Configure
  $(call Build/Configure/Default,--prefix= --with-embedded)
endef

define Build/Compile
  $(call Build/Compile/Default,LD=$(TARGET_CC))
endef

define Package/aprx/install
	$(INSTALL_DIR) $(1)/etc/init.d
        $(INSTALL_BIN) ./files/aprx.init $(1)/etc/init.d/aprx
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/aprx $(1)/usr/sbin/
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/aprx.conf $(1)/etc/aprx.conf
endef

$(eval $(call BuildPackage,aprx))
