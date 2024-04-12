include $(TOPDIR)/rules.mk

PKG_NAME:=libqtorrent
PKG_VERSION:=1.2.20
PKG_RELEASE=2024-01-18

PKG_SOURCE_PROTO:=git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/arvidn/libtorrent.git
PKG_SOURCE_DATE:=2024-01-18
PKG_SOURCE_VERSION:=2316136434d6785bc8c5d1b03add005e1a3945a9

PKG_MAINTAINER:=David Yang <mmyangfl@gmail.com>
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=COPYING

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/libqtorrent/Default
	TITLE:=C++ library implementing the BitTorrent protocol
	URL:=https://libtorrent.org/
endef

define Package/libqtorrent
	$(call Package/libqtorrent/Default)
	SECTION:=libs
	CATEGORY:=Libraries
	DEPENDS:=+boost-system +libopenssl +libatomic +libstdcpp
endef

define Package/libqtorrent/description
    libtorrent is an open source C++ library implementing the BitTorrent protocol
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/libtorrent $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libtorrent-rasterbar.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/libtorrent-rasterbar.pc $(1)/usr/lib/pkgconfig/
endef

define Package/libqtorrent/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libtorrent-rasterbar.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libqtorrent))
