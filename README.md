# androidsnippets

The root filesystem is a read-only initial ramdisk.  The contents of this ramdisk are present in `out/target/product/prodname/ramdisk.umg` which is a gzipped cpio archive.  Use `cp ramdisk.img ramdisktmp.gz ; gunzip ramdisktmp.gz ; cpio -itv < ramdisktmp` to see the contents.

The presence of the soft button navigation bar is controlled from `./frameworks/base/services/core/java/com/android/server/policy/PhoneWindowManager.java` which gets built into `out/target/product/smarc_mx6/system/framework/services.jar`.  (Deduced by time-stamp change and file-size increase after a rebuild.)

Properties can be set and get with setprop and getprop.  The properties in `/system/build.prop` are only read on a hard reboot, and not on an android reset.

The camera buttons seems to be triggered from `./frameworks/base/core/java/com/android/internal/policy/PhoneFallbackEventHandler.java`.

Key layout is in `./frameworks/base/data/keyboards/Vendor_03eb_Product_2042.kl` which builds to `/system/usr/keylayout/Vendor_03eb_Product_2042.kl`.

Pastebin:
```
chmod a+rw /dev/ttymxc4
logcat | grep blox
cat /dev/ttymxc4
/data/busybox/busybox stty -F /dev/ttymxc4
mount -o remount,rw /dev/block/mmcblk1p5 /system
/data/busybox/busybox vi
/data/busybox/busybox killall zygote
```
