# This is ProjectEverest [EverestOS]

# Build guide

Prior to building, you will need basic knowledge of [Git](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet).

### Requirements
- Around 350GB Disk Space.
- A computer with at least 32GB RAM (or 16 GB RAM + 48 GB swap, needed good SSD) running Linux (recommended) or MacOS.
- Build environment [setup](https://github.com/akhilnarang/scripts).

# Getting Started

### Initialize local repository

```
repo init -u https://github.com/Halhadus/everest-lindroid-manifest -b qpr3 --git-lfs
```

### Sync up 

```
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune -j$(nproc --all)
```

# Inherit the vendor
```
$(call inherit-product, vendor/everest/config/common_full_phone.mk)
```
# Build Flags
```
# Maintainer name for Everest

EVEREST_MAINTAINER := "XYZ"

# Adding Blur support

TARGET_SUPPORTS_BLUR := true

# For UDFPS devices

TARGET_HAS_UDFPS := true

EXTRA_UDFPS_ANIMATIONS := true

# Build GAPPS

WITH_GAPPS := true

# Build Vanilla

WITH_GAPPS := false

# Build Launcher3 in GAPPS (default is Pixel Launcher)

TARGET_INCLUDE_PIXEL_LAUNCHER := false
```

# Build

```
. build/envsetup.sh
export USE_CCACHE=1
ccache -M 50G
croot
lunch everest_marble-userdebug
mka bacon everest_marble-userdebug -j12 | tee log.txt
```

### Compilation Help
To get help with build errors, please visit [**Android Building Help**](https://t.me/AndroidBuildingHelp).

## Credits
 * [**The Parasite Project**](https://github.com/TheParasiteProject)
 * [**LineageOS**](https://github.com/LineageOS)
 * [**SuperiorOS**](https://github.com/superioros)
 * [**Project Awaken**](https://github.com/Project-Awaken)
 * [**ProtonAOSP**](https://github.com/ProtonAOSP)
 * [**PixelExperience**](https://github.com/PixelExperience)
 * [**Yet another AOSP project**](https://github.com/Yaap)
 * [**Pixel OS**](https://github.com/pixelos-aosp)
 * [**ProjectBlaze**](https://github.com/ProjectBlaze)
 * [**Superior Extended**](https://github.com/SuperiorExtended)
