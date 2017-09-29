# androidsnippets

The root filesystem is a read-only initial ramdisk.  The contents of this ramdisk are present in `out/target/product/prodname/ramdisk.umg` which is a gzipped cpio archive.  Use `cp ramdisk.img ramdisktmp.gz ; gunzip ramdisktmp.gz ; cpio -itv < ramdisktmp` to see the contents.

The presence of the soft button navigation bar is controlled from `./frameworks/base/services/core/java/com/android/server/policy/PhoneWindowManager.java` which gets built into `out/target/product/smarc_mx6/system/framework/services.jar`.  (Deduced by time-stamp change and file-size increase after a rebuild.)
