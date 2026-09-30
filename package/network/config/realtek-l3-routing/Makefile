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
 Turns on routing in the rtl83xx switch when network.globals.l3_offload
 is set. The switch then forwards every IPv4 route via its VLAN
 interfaces that it can hold and marks the routes offload, trap or
 offload_failed. IPv6 is not offloaded and so not routed while it is on.
endef

define Build/Compile
endef

define Package/realtek-l3-routing/install
	$(INSTALL_DIR) $(1)/etc/init.d $(1)/etc/sysctl.d
	$(INSTALL_BIN) ./files/realtek-l3.init $(1)/etc/init.d/realtek-l3
	$(INSTALL_DATA) ./files/realtek-l3.sysctl $(1)/etc/sysctl.d/90-realtek-l3.conf
endef

$(eval $(call BuildPackage,realtek-l3-routing))
