include $(TOPDIR)/rules.mk

PKG_NAME:=realtek-l3-routing
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0-only

include $(INCLUDE_DIR)/package.mk

define Package/realtek-l3-routing
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Route in the Realtek switch ASIC from UCI
  DEPENDS:=@TARGET_realtek
  PKGARCH:=all
endef

define Package/realtek-l3-routing/description
 Turns routing in the rtl83xx switch on or off from
 network.globals.l3_offload (default on). When it is off the kernel
 routes everything.
endef

define Build/Compile
endef

define Package/realtek-l3-routing/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/realtek-l3.init $(1)/etc/init.d/realtek-l3
endef

$(eval $(call BuildPackage,realtek-l3-routing))
