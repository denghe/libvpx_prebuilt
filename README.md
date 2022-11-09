# libvpx_prebuilt
how to build libvpx .lib .a

# offical git:
https://github.com/webmproject/libvpx

# 1. windows
https://github.com/ShiftMediaProject/VSYASM.git
https://github.com/ShiftMediaProject/libvpx.git

# 2. android
compile system: ubuntu / mac
download latest ndk or install by android studio

# create a directory like libvpx_armv7.  then create sub directory "jni"，enter,
```
git clone https://github.com/webmproject/libvpx
```

# create Android.mk
```
LOCAL_PATH := $(call my-dir)
include $(CLEAR_VARS)
include libvpx/build/make/Android.mk
```

# create Application.mk
```
APP_ABI := armeabi-v7a
APP_PLATFORM := android-33
APP_STL := c++_shared
APP_OPTIM := release

NDK_TOOLCHAIN_VERSION := 4.9
```

# execute following command:
```
./libvpx/configure --target=armv7-android-gcc --enable-external-build --disable-examples --disable-unit-tests --disable-tools --disable-docs --disable-vp8_encoder --disable-vp8_decoder --disable-vp9_encoder --disable-webm_io --disable-libyuv
```

then, call "ndk-build" like   ~/Android/Sdk/ndk/25.1.8937393/ndk-build 

# arm64
```
--target=arm64-android-gcc        APP_ABI := arm64-v8a
```

3. mac/ios
todo
