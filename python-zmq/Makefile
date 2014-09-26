#
# Copyright (C) 2014 OpenWrt.org
#
# Author: Mikolaj Chwalisz <chwalisz@tkn.tu-berlin.de>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pyzmq
PKG_VERSION:=14.3.1
PKG_RELEASE:=1

PKG_SOURCE:=pyzmq-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/p/pyzmq/
PKG_MD5SUM:=7196b4a6fbf98022f17ffa924be3d68d

PKG_BUILD_DIR:=$(BUILD_DIR)/pyzmq-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/pyzmq
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=pyzmq
  URL:=http://zeromq.org/bindings:python
  DEPENDS:=+python +zeromq
endef

define Package/pyzmq/description
  This package contains Python bindings for ØMQ. ØMQ is a lightweight and
  fast messaging implementation.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix="$(PKG_INSTALL_DIR)/usr")
endef

define Package/pyzmq/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
	    $(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
	    $(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,pyzmq))
