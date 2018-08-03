# pplus-tmo-archlinux-boot

LG H901 boot image modified to boot an Arch Linux rootfs using initscripts-fork.
Note: This will disable any download mode/LGUP functionality on your device. You have been forewarned.

To install:
- Boot into TWRP
- Open an ADB shell
- cd to where you have copied this boot image
- Backup your laf partition, this is for LG Download Mode:
run: dd if=/dev/block/bootdevice/by-name/laf of=lafbak.img
- Wipe the laf partition:
run: dd if=/dev/zero of=/dev/block/bootdevice/by-name/laf
- Flash the boot image:
run: dd if=boot.img of=/dev/block/bootdevice/by-name/laf

To boot into this boot image, just simply power off your device, then plug the USB cable into a computer while holding the volume up button.
This REPLACES download mode.

I have also included the initrd, kernel, and dtb file.
