Linux Device Tree Blob for the Banana Pi - M64
===============================================

This is Device Tree Blob with correct settings for the BananaPi M64 running linux and kernel 3.10.10X with following:

- eMMC (enabled)
- Wifi (enabled)
- BT (enabled)
- OV5640 (not tested - need revision)
- HDMI 1080P
- OTG (missing some bits - need a fix)

Instructions
=============

- Make a copy of your current sun50i-a64-pine64-plus.dtb (backup)


	mv /media/BPI-BOOT/bananapi/bpi-m64/linux/pine64-plus.dtb /media/BPI-BOOT/bananapi/bpi-m64/linux/pine64-plus.dtb_OK



- Copy the new DTB to the boot partition


	cp -v sun50i-a64-pine64-plus.dtb /media/BPI-BOOT/bananapi/bpi-m64/linux/pine64-plus.dtb

	sync

- Reboot


If you find errors or misleading info in the instructions, please let me known and i will fix it ASAP.

History Log:
* initial commit

