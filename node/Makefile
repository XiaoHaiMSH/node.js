# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=node
PKG_RELEASE:=1

ifeq ($(CONFIG_NODEJS_22),y)
PKG_VERSION:=22.23.3
NODE_MODULE_VERSION:=127
else ifeq ($(CONFIG_NODEJS_26),y)
PKG_VERSION:=26.11.1
NODE_MODULE_VERSION:=147
else
PKG_VERSION:=24.21.0
NODE_MODULE_VERSION:=137
endif

ifeq ($(ARCH),aarch64)
NODE_ARCH:=arm64
else ifeq ($(ARCH),x86_64)
NODE_ARCH:=x64
endif

PKG_SOURCE:=node-v$(PKG_VERSION)-linux-$(NODE_ARCH)-musl.tar.xz
PKG_SOURCE_URL:=https://unofficial-builds.nodejs.org/download/release/v$(PKG_VERSION)/
PKG_HASH:=skip
PKG_BUILD_DIR:=$(BUILD_DIR)/node-v$(PKG_VERSION)-linux-$(NODE_ARCH)-musl

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_CPE_ID:=cpe:/a:nodejs:node.js

include $(INCLUDE_DIR)/package.mk

define Package/node
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Node.js
  TITLE:=Node.js is a platform built on Chrome's JavaScript runtime
  URL:=https://nodejs.org/
  DEPENDS:=@(x86_64||aarch64) +libstdcpp
  ABI_VERSION:=$(NODE_MODULE_VERSION)
endef

define Package/node/description
  Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine. Node.js uses
  an event-driven, non-blocking I/O model that makes it lightweight and efficient. Node.js'
   package ecosystem, npm, is the largest ecosystem of open source libraries in the world.
endef

define Package/node-npm
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Node.js
  TITLE:=NPM stands for Node Package Manager
  URL:=https://www.npmjs.com/
  DEPENDS:=+node
endef

define Package/node-npm/description
  NPM is the package manager for NodeJS
endef

define Package/node/config
	menu "Configuration"

	choice
		prompt "Version Selection"
		default NODEJS_24
		help
		 Select node.js version.

		config NODEJS_22
			bool "22.x Maintenance LTS"

		config NODEJS_24
			bool "24.x Active LTS"

		config NODEJS_26
			bool "26.x Current"
	endchoice

	endmenu
endef

define Build/Configure
endef

define Build/Compile
	[ "$(NODE_ARCH)" != "x64" ] || { \
		perl -0777 -pi -e 's/\0libc\.musl-x86_64\.so\.1\0/"\0libc.so" . "\0" x 15/e' $(PKG_BUILD_DIR)/bin/node && \
		$(TARGET_CROSS)readelf -d $(PKG_BUILD_DIR)/bin/node | grep -q 'Shared library: \[libc\.so\]'; \
	}
endef

define Package/node/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/node $(1)/usr/bin/
endef

define Package/node-npm/install
	$(INSTALL_DIR) $(1)/usr/lib/node_modules/npm
	$(CP) $(PKG_BUILD_DIR)/lib/node_modules/npm/{package.json,LICENSE,README.md} \
		$(1)/usr/lib/node_modules/npm/
	$(CP) $(PKG_BUILD_DIR)/lib/node_modules/npm/{node_modules,bin,lib} \
		$(1)/usr/lib/node_modules/npm/
	$(INSTALL_DIR) $(1)/usr/bin
	$(LN) ../lib/node_modules/npm/bin/npm-cli.js $(1)/usr/bin/npm
	$(LN) ../lib/node_modules/npm/bin/npx-cli.js $(1)/usr/bin/npx
endef

define Package/node-npm/postrm
#!/bin/sh
rm -rf /usr/lib/node_modules/npm || true
endef

$(eval $(call BuildPackage,node))
$(eval $(call BuildPackage,node-npm))
