# مشروع Sovereign V41

THEOS_DEVICE_IP = localhost
THEOS_DEVICE_PORT = 2222
ARCHS = arm64 arm64e
TARGET = iphone:clang:latest:13.0
DEBUG = 0
PACKAGE_VERSION = 4.1.0

include $(THEOS)/makefiles/common.mk

TWEAK_NAME = SovereignV41
SovereignV41_FILES = SovereignSecurity.m
SovereignV41_CFLAGS = -fobjc-arc
SovereignV41_FRAMEWORKS = UIKit Foundation Security CoreML Vision
SovereignV41_PRIVATE_FRAMEWORKS = GameController
SovereignV41_LIBRARIES = substrate
SovereignV41_EXTRA_FRAMEWORKS = CydiaSubstrate

include $(THEOS_MAKE_PATH)/tweak.mk

after-install::
	install.exec "killall -9 SpringBoard"

SUBPROJECTS += sovereignprefs
include $(THEOS_MAKE_PATH)/aggregate.mk