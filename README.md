Mali r7p0 kernel driver for Rockchip 
===============================================

```
export ARCH=arm
export CROSS_COMPILE=arm-linux-gnueabihf-
export KDIR=/lib/modules/$(uname -r)/build
./build.sh
```

Copy mali.ko to /lib/modules into your kernel modules directory, then

```
depmod -a
modprobe mali
```

Then you should be able to use rockchip r7p0 userland mali libraries you can find here:

https://github.com/rockchip-linux/libmali

Mali libraries should have the following symlinks :
```
libEGL.so -> libEGL.so.1
libEGL.so.1 -> libEGL.so.1.4
libEGL.so.1.4 -> libMali.so
libGLESv1_CM.so -> libGLESv1_CM.so.1
libGLESv1_CM.so.1 -> libGLESv1_CM.so.1.1
libGLESv1_CM.so.1.1 -> libMali.so
libGLESv2.so -> libGLESv2.so.2
libGLESv2.so.2 -> libGLESv2.so.2.0
libGLESv2.so.2.0 -> libMali.so
libMali.so
```
