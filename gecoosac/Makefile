include $(TOPDIR)/rules.mk

PKG_NAME:=gecoosac
PKG_VERSION:=2.2.20251015
PKG_RELEASE:=1

# 【修改点1】直接写死架构，不判断了
PKG_ARCH:=ac_linux_arm64
PKG_HASH:=skip

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(ARCH_PACKAGES)
# 注意：原作者这里的 URL 有个问号，保留它
PKG_SOURCE_URL:=https://github.com/lwb1978/gecoosac-core/releases/download/V$(PKG_VERSION)/$(PKG_ARCH)?
UNPACK_CMD=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/$(PKG_NAME)

PKG_LICENSE:=AGPL-3.0-only
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=lwb1978 <lwb1978@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=net
  CATEGORY:=Network
  TITLE:=gecoosac server (version $(PKG_VERSION))
  URL:=http://www.cnrouter.com/
  # 【修改点2】解除门禁，改为通用依赖
  DEPENDS:=+libc
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/bin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
