ifeq ($(THEOS_PACKAGE_SCHEME),rootless)
	ARCHS = arm64 arm64e
else ifdef ONLY_ARM64
	ARCHS = arm64 arm64e
else
	ARCHS = armv7 armv7s arm64 arm64e
endif

include $(THEOS)/makefiles/common.mk

TOOL_NAME = postinst prerm

postinst_FILES = pkg-actions.m
postinst_CFLAGS += -fobjc-arc -fvisibility=hidden -DPOSTINST
postinst_FRAMEWORKS = CoreFoundation
postinst_INSTALL_PATH = /DEBIAN
postinst_CODESIGN_FLAGS = -S../entitlements.plist

prerm_FILES = pkg-actions.m
prerm_CFLAGS += -fobjc-arc -fvisibility=hidden
prerm_FRAMEWORKS = CoreFoundation
prerm_INSTALL_PATH = /DEBIAN
prerm_CODESIGN_FLAGS = -S../entitlements.plist

include $(THEOS_MAKE_PATH)/tool.mk
