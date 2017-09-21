# androidsnippets

The root filesystem is a read-only initial ramdisk.  The contents of this ramdisk are present in `out/target/product/prodname/ramdisk.umg` which is a gzipped cpio archive.  Use `cp ramdisk.img ramdisktmp.gz ; gunzip ramdisktmp.gz ; cpio -itv < ramdisktmp` to see the contents.
