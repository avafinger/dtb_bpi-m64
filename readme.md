Linux Device Tree Blob for the Banana Pi M64
============================================

This is Device Tree Blob with correct settings for the BananaPi M64 running linux and kernel 3.10.10X with following:

- eMMC (enabled) (need a dirty hack for now)
- Wifi (enabled) (fix up)
- BT (enabled) (fix up)
- OV5640 (enabled)
- HDMI 1080P
- GbE (enabled)
- OTG (need a fix)
- Gpio (not activated for now)
- Uart (not activate for now)

Instructions
=============

- Make a copy of your current sun50i-a64-pine64-plus.dtb (backup)


	mv /media/BPI-BOOT/bananapi/bpi-m64/linux/pine64-plus.dtb /media/BPI-BOOT/bananapi/bpi-m64/linux/pine64-plus.dtb_OK



- Copy the new DTB to the boot partition


	cp -v sun50i-a64-pine64-plus.dtb /media/BPI-BOOT/bananapi/bpi-m64/linux/pine64-plus.dtb

	sync

- Reboot


If you find errors or misleading info in the instructions, please let me know and i will fix it ASAP.

History Log:
===========
* initial commit
* Fix for Wifi/BT (Ampak ap6212) - ** Updated **
* Added kernel config
* Added Ampak firmware (latest)

Log:
====


	Module                  Size  Used by
	bnep                   17511  2
	ov5640                 50600  0
	dw9714_act             12833  0
	actuator               12385  1 dw9714_act
	hci_uart               27742  0
	bluetooth             195943  6 bnep,hci_uart
	vfe_v4l2              747618  0
	videobuf2_dma_contig    17668  1 vfe_v4l2
	videobuf2_memops       12546  1 videobuf2_dma_contig
	videobuf2_core         30952  1 vfe_v4l2
	ir_sanyo_decoder       12491  0
	ir_lirc_codec          12756  0
	ir_rc5_decoder         12487  0
	ir_sony_decoder        12489  0
	ir_rc6_decoder         12520  0
	ir_nec_decoder         12487  0
	lirc_dev               17032  1 ir_lirc_codec
	ir_mce_kbd_decoder     12628  0
	cedar_ve               17368  0
	ss                     37179  0
	ir_jvc_decoder         12487  0
	vfe_io                 34085  3 vfe_v4l2,ov5640,dw9714_act
	sunxi_ir_rx            12902  0
	bcmdhd                624241  0
	cfg80211              374207  1 bcmdhd



	[   16.791364] sunxi-gmac 1c30000.eth eth0: eth0: PHY ID 001cc915 at 0 IRQ poll (1c30000.eth-0:00)
	[   22.686767] libphy: 1c30000.eth-0:00 - Link is Up - 1000/Full
	[   59.570681] EXT4-fs (mmcblk0p7): warning: mounting fs with errors, running e2fsck is recommended
	[   59.573379] EXT4-fs (mmcblk0p7): mounted filesystem with ordered data mode. Opts: (null)
	[   59.648057] FAT-fs (mmcblk0p2): Volume was not properly unmounted. Some data may be corrupt. Please run fsck.
	[   59.729363] EXT4-fs (mmcblk0p16): mounted filesystem with ordered data mode. Opts: (null)
	[   59.806269] EXT4-fs (mmcblk0p11): mounted filesystem with ordered data mode. Opts: (null)
	[  225.640140] cfg80211: Calling CRDA to update world regulatory domain
	[  225.714750] dhd_module_init: in
	[  225.714767] ======== bcm_wlan_set_plat_data ========
	[  225.714779] host_oob_irq: 4 
	[  225.714783] host_oob_irq_flags=16516
	[  225.714787] dhd_wifi_platform_load: Enter
	[  225.714822] Power-up adapter 'DHD generic adapter'
	[  225.714877] wifi_platform_set_power = 1
	[  225.714882] ======== PULL WL_REG_ON HIGH! ========
	[  225.715560] sunxi-wlan wlan.27: check wlan wlan_power voltage: 3300000
	[  225.715768] sunxi-wlan wlan.27: check wlan io_regulator voltage: 3300000
	[  225.730414] cfg80211: World regulatory domain updated:
	[  225.730431] cfg80211:   (start_freq - end_freq @ bandwidth), (max_antenna_gain, max_eirp)
	[  225.730437] cfg80211:   (2402000 KHz - 2472000 KHz @ 40000 KHz), (N/A, 2000 mBm)
	[  225.730442] cfg80211:   (2457000 KHz - 2482000 KHz @ 40000 KHz), (N/A, 2000 mBm)
	[  225.730447] cfg80211:   (2474000 KHz - 2494000 KHz @ 20000 KHz), (N/A, 2000 mBm)
	[  225.730452] cfg80211:   (5170000 KHz - 5250000 KHz @ 80000 KHz), (N/A, 2000 mBm)
	[  225.730457] cfg80211:   (5250000 KHz - 5330000 KHz @ 80000 KHz), (N/A, 2000 mBm)
	[  225.730462] cfg80211:   (5490000 KHz - 5730000 KHz @ 160000 KHz), (N/A, 2000 mBm)
	[  225.730467] cfg80211:   (5735000 KHz - 5835000 KHz @ 80000 KHz), (N/A, 2000 mBm)
	[  225.730472] cfg80211:   (57240000 KHz - 63720000 KHz @ 2160000 KHz), (N/A, 0 mBm)
	[  226.026266] wifi_platform_bus_enumerate device present 1
	[  226.026302] sunxi-wlan wlan.27: bus_index: 1
	[  226.026312] ======== Card detection to detect SDIO card! ========
	[  226.026384] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 0Hz bm PP pm UP vdd 21 width 1 timing LEGACY(SDR12) dt B
	[  226.026539] sunxi-mmc 1c10000.sdmmc: no vqmmc,Check if there is regulator
	[  226.045923] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 400000Hz bm PP pm ON vdd 21 width 1 timing LEGACY(SDR12) dt B
	[  226.066396] sunxi-mmc 1c10000.sdmmc: smc 2 p1 err, cmd 52, RTO !!
	[  226.073987] sunxi-mmc 1c10000.sdmmc: smc 2 p1 err, cmd 52, RTO !!
	[  226.080785] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 400000Hz bm PP pm ON vdd 21 width 1 timing LEGACY(SDR12) dt B
	[  226.083211] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 400000Hz bm PP pm ON vdd 21 width 1 timing LEGACY(SDR12) dt B
	[  226.085062] sunxi-mmc 1c10000.sdmmc: smc 2 p1 err, cmd 8, RTO !!
	[  226.092097] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 400000Hz bm PP pm ON vdd 16 width 1 timing LEGACY(SDR12) dt B
	[  226.101314] mmc2: queuing unknown CIS tuple 0x80 (2 bytes)
	[  226.102856] mmc2: queuing unknown CIS tuple 0x80 (3 bytes)
	[  226.104401] mmc2: queuing unknown CIS tuple 0x80 (3 bytes)
	[  226.107192] mmc2: queuing unknown CIS tuple 0x80 (7 bytes)
	[  226.194918] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 400000Hz bm PP pm ON vdd 16 width 1 timing SD-HS(SDR25) dt B
	[  226.194997] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 50000000Hz bm PP pm ON vdd 16 width 1 timing SD-HS(SDR25) dt B
	[  226.195119] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 50000000Hz bm PP pm ON vdd 16 width 4 timing SD-HS(SDR25) dt B
	[  226.197825] mmc2: new high speed SDIO card at address 0001
	[  226.201279] *mmc2 lock timeout*
	[  226.217229] bcmsdh_register: register client driver
	[  226.217432] bcmsdh_sdmmc: bcmsdh_sdmmc_probe Enter
	[  226.217568] bcmsdh_sdmmc: bcmsdh_sdmmc_probe Enter
	[  226.217581] bus num (host idx)=2, slot num (rca)=1
	[  226.217591] found adapter info 'DHD generic adapter'
	[  226.218015] dhdsdio_probe : no mutex held. set lock
	[  226.218151] F1 signature read @0x18000000=0x1540a9a6
	[  226.221693] F1 signature OK, socitype:0x1 chip:0xa9a6 rev:0x0 pkg:0x4
	[  226.224361] DHD: dongle ram size is set to 524288(orig 524288) at 0x0
	[  226.224541] dhd_conf_set_chiprev: chip=0xa9a6, chiprev=0
	[  226.224639] dhd_conf_set_conf_path_by_nv_path: config_path=/lib/firmware/ap6212/config.txt
	[  226.247981] tsk Enter, tsk = 0xffffffc0641419c0
	[  226.248004] wl_create_event_handler(): thread:wl_event_handler:411 started
	[  226.248253] dhd_attach(): thread:dhd_watchdog_thread:412 started
	[  226.248298] dhd_dpc_thread: set dpc_cpucore 0 from config.txt
	[  226.248323] dhd_attach(): thread:dhd_dpc:413 started
	[  226.248370] dhd_attach(): thread:dhd_rxf:414 started
	[  226.248384] dhd_deferred_work_init: work queue initialized 
	[  226.248523] dhdsdio_probe_init: set use_rxchain 1 from config.txt
	[  226.254630] Dongle Host Driver, version 1.201.59.3 (r506368)
	               Compiled in drivers/net/wireless/bcmdhd on Jan 21 2017 at 01:48:08
	[  226.257192] Register interface [wlan0]  MAC: 94:a1:a2:c2:55:46
	
	[  226.257213] dhd_prot_ioctl : bus is down. we have nothing to do
	[  226.257274] bcmsdh_oob_intr_unregister: Enter
	[  226.257279] bcmsdh_oob_intr_unregister: irq is not registered
	[  226.257290] dhd_txglom_enable: enable 0
	[  226.257294] dhd_bus_devreset:  WLAN OFF DONE
	[  226.257332] wifi_platform_set_power = 0
	[  226.257336] ======== PULL WL_REG_ON LOW! ========
	[  226.257693] dhdsdio_probe : the lock is released.
	[  226.257813] dhd_module_init: Exit err=0
	[  226.313776] dhd_open: Enter ffffffc07698d000
	[  226.313798] 
	               Dongle Host Driver, version 1.201.59.3 (r506368)
	               Compiled in drivers/net/wireless/bcmdhd on Jan 21 2017 at 01:48:08
	[  226.313806] wl_android_wifi_on in 1
	[  226.313811] wl_android_wifi_on in 2: g_wifi_on=0
	[  226.313816] wifi_platform_set_power = 1
	[  226.313820] ======== PULL WL_REG_ON HIGH! ========
	[  226.315825] sunxi-wlan wlan.27: check wlan wlan_power voltage: 3300000
	[  226.317175] sunxi-wlan wlan.27: check wlan io_regulator voltage: 3300000
	[  226.626526] sdio_reset_comm():
	[  226.626577] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 50000000Hz bm PP pm ON vdd 16 width 4 timing SD-HS(SDR25) dt B
	[  226.628680] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 50000000Hz bm PP pm ON vdd 16 width 4 timing SD-HS(SDR25) dt B
	[  226.629713] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 400000Hz bm PP pm ON vdd 16 width 4 timing LEGACY(SDR12) dt B
	[  226.630097] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 400000Hz bm PP pm ON vdd 16 width 4 timing LEGACY(SDR12) dt B
	[  226.642521] mmc2: queuing unknown CIS tuple 0x80 (2 bytes)
	[  226.644068] mmc2: queuing unknown CIS tuple 0x80 (3 bytes)
	[  226.645615] mmc2: queuing unknown CIS tuple 0x80 (3 bytes)
	[  226.648811] mmc2: queuing unknown CIS tuple 0x80 (7 bytes)
	[  226.735921] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 400000Hz bm PP pm ON vdd 16 width 4 timing SD-HS(SDR25) dt B
	[  226.736017] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 50000000Hz bm PP pm ON vdd 16 width 4 timing SD-HS(SDR25) dt B
	[  226.736138] sunxi-mmc 1c10000.sdmmc: sdc set ios: clk 50000000Hz bm PP pm ON vdd 16 width 4 timing SD-HS(SDR25) dt B
	[  226.736685] 
	               
	               dhd_bus_devreset: == WLAN ON ==
	[  226.736839] F1 signature read @0x18000000=0x1540a9a6
	[  226.740238] F1 signature OK, socitype:0x1 chip:0xa9a6 rev:0x0 pkg:0x4
	[  226.741502] DHD: dongle ram size is set to 524288(orig 524288) at 0x0
	[  226.741860] dhdsdio_probe_init: set use_rxchain 1 from config.txt
	[  226.742249] dhd_conf_set_fw_name_by_chip: firmware_path=/lib/firmware/ap6212/fw_bcm43438a0.bin
	[  226.742262] Final fw_path=/lib/firmware/ap6212/fw_bcm43438a0.bin
	[  226.742271] Final nv_path=/lib/firmware/ap6212/nvram.txt
	[  226.742280] Final conf_path=/lib/firmware/ap6212/config.txt
	[  226.802478] NVRAM version: AP6212_NVRAM_V1.0_20140603
	[  226.803286] dhdsdio_write_vars: Download, Upload and compare of NVRAM succeeded.
	[  226.860237] dhd_bus_init: enable 0x06, ready 0x06 (waited 0us)
	[  226.860383] bcmsdh_oob_intr_register: Enter
	[  226.860394] bcmsdh_oob_intr_register: HW_OOB enabled
	[  226.860404] bcmsdh_oob_intr_register OOB irq=4 flags=4084
	[  226.860536] bcmsdh_oob_intr_register: enable_irq_wake
	[  226.861459] dhd_conf_set_band: Set band 0
	[  226.865660] Firmware up: op_mode=0x0005, MAC=94:a1:a2:c2:55:46
	[  226.865671] dhd_conf_set_country: Set country CN, revision 0
	[  226.929411] Country code: CN (CN/0)
	[  226.930072] dhd_conf_set_roam: Set roam_off 1
	[  226.943686] Firmware version = wl0: Jul 18 2014 18:24:48 version 7.10.226.54.x2 (A0 Station) FWID 01-2faae407
	[  226.943700]   Driver: 1.201.59.3 (r506368)
	                 Firmware: wl0: Jul 18 2014 18:24:48 version 7.10.226.54.x2 (A0 Station) FWID 01-2faae407 
	[  226.944104] dhd_txglom_enable: enable 1
	[  226.944115] dhd_conf_set_disable_proptx: set disable_proptx 0
	[  226.946406] dhd_wlfc_hostreorder_init(): successful bdcv2 tlv signaling, 64
	[  226.946949] wl_android_wifi_on: Success
	[  227.021686] dhd_open: Exit ret=0
	[  227.240416] WLC_E_IF: NO_IF set, event Ignored
	[  355.644454] EXT4-fs (mmcblk0p7): error count since last fsck: 51
	[  355.644478] EXT4-fs (mmcblk0p7): initial error at time 1483747057: ext4_find_entry:1309: inode 2
	[  355.644496] EXT4-fs (mmcblk0p7): last error at time 1483748056: ext4_put_super:768: inode 2
	[  372.603495] Bluetooth: Core ver 2.16
	[  372.603593] NET: Registered protocol family 31
	[  372.603598] Bluetooth: HCI device and connection manager initialized
	[  372.603634] Bluetooth: HCI socket layer initialized
	[  372.603643] Bluetooth: L2CAP socket layer initialized
	[  372.603661] Bluetooth: SCO socket layer initialized
	[  372.674111] Bluetooth: HCI UART driver ver 2.2
	[  372.674125] Bluetooth: HCI H4 protocol initialized
	[  372.674129] Bluetooth: HCI BCSP protocol initialized
	[  372.674133] Bluetooth: HCILL protocol initialized
	[  372.674138] Bluetooth: HCIATH3K protocol initialized
	[  372.674142] Bluetooth: HCI Three-wire UART (H5) protocol initialized


